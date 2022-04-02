# Docker Projects

This repo includes some projects and general useful Docker commands

## Useful Docker Commands

* Check docker version: `docker --version`
* Search the Docker Hub for images: `docker search IMAGE`
* Pull an image from Docker Hub: `docker pull IMAGE`
* Show the history of an image: `docker history IMAGE`
* List docker images: `docker images`
* List running containers: `docker ps`
* List all containers: `docker ps -a`
* Run a container interactively: `docker run -it IMAGE`
* Run a container in the background: `docker run -d IMAGE`
* Use flag `-w` to set a working directory inside the container
* Use flag `-v` to mount a volume into the container
* Use flg `-ENV` to using an enviromnent variable with the `docker run` command
* Delete all images: `docker rmi -f $(docker images -q)`
* Delete all containers: `docker rm -f $(docker ps -a -q)`
* Build an image from Dockerfile: `docker build -t IMAGE-TAG .`
* Specify a Dockerfile using `-f`: `docker build -f SPECIFIED DOCKERFILE .`
* Expose a port from host to container: `docker run -dp HOST-PORT:CONTAINER-PORT IMAGE`
* Watch containers: `watch docker ps`
* Save an image into a tar archive: `docker save -o NAME.tar IMAGE`
* Load an image from a tar archive: `docker load -i NAME.tar`
* Tag an image: `docker tag IMAGE IMAGE:TAG`
* Export a container’s filesystem as a tar archive after you apply some modifications inside the container: `docker export --output="NAME.tar" CONTAINER`
* Access the shell of last created container: `docker exec -it $(docker ps -l -q) /bin/sh`
* List contents of tar archive: `tar -tvf NAME.tar`
* Import a container's filesystem tar archive into an image: `docker import NAME.tar IMAGE:TAG`
* Example of modifying an image imported from a container's filesystem tar archive: `docker import -c 'WORKDIR /app' -c 'ENTRYPOINT ["python"]' -c 'CMD ["app.py"]' test.tar dev:test`
* Create a docker volume: `docker volume create VOL-NAME`
* Inspect a created volume: `docker volume inspect VOL-NAME`
* Mountpoint of the created volume is `/var/lib/docker/volumes/NAME/_data`
* Create a container and mount a created volume: `docker run -dp HOST-PORT:CONTAINER-PORT --name NAME --mount source=VOL-NAME,target=CONTAINER-PATH dev1`