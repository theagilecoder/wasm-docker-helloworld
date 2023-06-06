Docker image based on ubuntu with wasmer runtime installed 
https://wasmer.io/

and runs a simple helloworld program written in wasm
https://wapm.io/bjfish/helloworld

```console
***@pop-os:~/wasm$ sudo docker build -t wasm-helloworld .
[+] Building 1.1s (9/9) FINISHED                                                                                                                                                      
 => [internal] load build definition from Dockerfile                                                                                                                             0.0s
 => => transferring dockerfile: 511B                                                                                                                                             0.0s
 => [internal] load .dockerignore                                                                                                                                                0.0s
 => => transferring context: 2B                                                                                                                                                  0.0s
 => [internal] load metadata for docker.io/library/ubuntu:latest                                                                                                                 0.9s
 => [1/4] FROM docker.io/library/ubuntu:latest@sha256:ac58ff7fe25edc58bdf0067ca99df00014dbd032e2246d30a722fa348fd799a5                                                           0.0s
 => [internal] load build context                                                                                                                                                0.0s
 => => transferring context: 38B                                                                                                                                                 0.0s
 => CACHED [2/4] RUN apt-get update && apt-get install -y curl                                                                                                                   0.0s
 => CACHED [3/4] RUN curl https://get.wasmer.io -sSfL | sh                                                                                                                       0.0s
 => CACHED [4/4] COPY helloworld.wasm ./                                                                                                                                         0.0s
 => exporting to image                                                                                                                                                           0.0s
 => => exporting layers                                                                                                                                                          0.0s
 => => writing image sha256:f7a10d5c20863951db925e95aee7aebeaa1b473f9b2ee3b82415bba0d21f3811                                                                                     0.0s
 => => naming to docker.io/library/wasm-helloworld                                                                                                                               0.0s
***@pop-os:~/wasm$ sudo docker run -it docker.io/library/wasm-helloworld
Hello, WAPM & WASI!

```
