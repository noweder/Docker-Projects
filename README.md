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
* Remove the created container once exited: `docker run --rm --name CONTAINER-NAME IMAGE-NAME`
* Creating a `.dockerignore` file in the same `Dockerfile` level, and listing file names inside it, will ignore copying these files into the docker image you build.
* Run a `docker-compose.yml` file using `docker-compose up`. If you want to run it in detach mode, use `docker-compose up -d`
* Run `docker-compose down` to kill everything created by `docker-compose`. However, any created volumes will still retain. To auto remove created volumes, you can use the flag `-v`
* Volumes created and mounted with containers can be found in `/var/lib/docker/volumes` directory.
* Copy files/folders between a container and the local filesystem using `docker cp CONTAINER_NAME:SRC_PATH DEST_PATH`
* Run the following example command to list the databases in postgres: `docker exec -it postgres psql -d noweder-db -U hamza -c "\l"`
* Use the following example command to stop and remove container image : `docker-compose rm -s postgres`
* Use the following example command to remove a volume: `docker volume rm VOL-NAME`
* Use the following example command to list database tables: `docker exec -it postgres psql -d noweder-db -U hamza -c "\dt"`
* Use the following example command to list all table content: `docker exec -it postgres psql -d noweder-db -U hamza -c "select * from temperature_data"`
* 