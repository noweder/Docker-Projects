# Simple APP deployment on Docker

This is a an example on how to deploy a web server app on a docker container. You first need to clone this repo and then access the dev1 folder. Then you can build a docker image using the following command: `docker build -t <NAME-OF-IMAGE> -f <SPECIFY-WHICH-DOCKERFILE> .`

After you create the image, you can run a docker container using the following command: `docker run -dp <HOST-PORT:5000> <NAME-OF-IMAGE>`

You can then verify connectivity from the host to the web server running in the container using the following command: `curl localhost:<HOST-PORT>`

To check if the container is healthy or not, you can use to the following to command to watch the health state: `watch docker ps`

