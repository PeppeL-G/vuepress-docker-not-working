# VuePress 2 not Working in Docker

## Running locally works
1. `cd vuepress-app`
2. `npm install`
3. `npm run docs:dev`
4. Open [localhost:8080](http://localhost:8080/) in a web browser

## Running in Docker does not work
1. `docker-compose up --build`

Looking at the last two lines in the output below, VuePress should be up and running, but opening [localhost:8080](http://localhost:8080/) in the web browsers times out after a while, and line 2 below (`9/10`) suggest the build is not finished, and the timer (`70.0s`) continues to tick.

```
 => [6/6] RUN npm run Building vuepress-app
[+] Building 70.0s (9/10)
 => [internal] load build definition from Dockerfile                                                                                                                            0.0s
 => => transferring dockerfile: 32B                                                                                                                                             0.0s
 => [internal] load .dockerignore                                                                                                                                               0.0s
 => => transferring context: 2B                                                                                                                                                 0.0s
 => [internal] load metadata for docker.io/library/node:lts-alpine                                                                                                              1.3s
 => [1/6] FROM docker.io/library/node:lts-alpine@sha256:8f1827381eb7fca5a79ad21cb42e935546bedf67d9f668519a7db69d77d812bf                                                        0.0s
 => [internal] load build context                                                                                                                                               0.0s
 => => transferring context: 1.54kB                                                                                                                                             0.0s
 => CACHED [2/6] WORKDIR /vuepress-app                                                                                                                                          0.0s
 => CACHED [3/6] COPY ./package*.json ./                                                                                                                                        0.0s
 => CACHED [4/6] RUN npm install                                                                                                                                                0.0s
 => CACHED [5/6] COPY ./docs/ ./docs                                                                                                                                            0.0s
 => [6/6] RUN npm run docs:dev                                                                                                                                                 68.6s
 => => # info Initializing VuePress and preparing data...
 => => # - Compiling with webpack...
 => => # ✔ Compilation finished in 5339ms
 => => # success VuePress webpack dev server is listening at http://localhost:8080/
 => => # webpack compiled successfully
```

The counter ()