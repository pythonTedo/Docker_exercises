# Docker exercises
## Simple-node

### Overview
This is a very simple, bare-bones NodeJS project created for you to use with Docker.

### Local Setup
* Install dependencies: `npm install`
* Run server: `node server.js`

### Container Setup
* Build image: `docker build .`
* Run container with image: `docker run {image_id}` where `image_id` can be retrieved by running `docker images` and found under the column `IMAGE ID`

### Container teardown
* Remove container: `docker kill {container_id}` where `container_id` can be retrieved by running `docker ps` and found under the column `CONTAINER ID`

## Debugging-containers
    When run container see log files
    * `docker run -d image`
    * `docker logs image`
    * `docker inspect`

## Slow node 
### in order to be fast when we want docker to build the image. We build base image and we will use it.

1. We crate in /base-image where we install all node setup and entrypoint is CMD ['node']
2. Docker hub login: docker login --username ...
3. We tag it: docker tag teodorchakarov/node-slow-base
4. We push the image to the repo

5. After that in our original Dockerfile we chamge FROM teodorchakarov/node-slow-base and its going to pull the base image from the repo.