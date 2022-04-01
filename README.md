# Docker Projects

This repo includes some projects and general useful Docker commands

## Useful Docker Commands

* Check docker version: `docker --version`
* Search the Docker Hub for images: `docker search IMAGE`
* Pull an image from Docker Hub: `docker pull IMAGE`
* Show the history of an image: `docker history IMAGE`
* 
* List docker images: `docker images`
* List running containers: `docker ps`
* List all containers: `docker ps -a`
* Run a container interactively: docker run -it IMAGE
* Run a container in the background: docker run -d IMAGE
* Use flag `-w` to set a working directory inside the container
* User flag `-v` to mount a volume into the container
* Delete all images: `docker rmi -f $(docker images -a -q)`
* Delete all containers: `docker rm $(docker ps -a -q)`
* Build an image from Dockerfile: `docker build -t IMAGE-TAG .`
* Specify a Dockerfile using `-f`: `docker build -f SPECIFIED DOCKERFILE .`
* Expose a port from host to container: `docker run -dp HOST-PORT:CONTAINER-PORT IMAGE`
* Watch containers: watch docker ps
* Save an image into a tar archive: `docker save -o NAME.tar IMAGE`
* Load an image from a tar archive: `docker load -i NAME.tar`
* Tag an image: `docker tag IMAGE IMAGE:TAG`