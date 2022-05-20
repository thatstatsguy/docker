#Basics
**Run your first container**

`docker run --rm -p 8787:8787 -e PASSWORD=yourpasswordhere rocker/rstudio`

**List all containers, running or exited**

`docker ps -a`

**Delete a running container**

`docker rm <ConainerName> -f`

**List docker images available**

`docker images`

#Intermediate

**Build new image from existing (running) container**

Extract from https://thenewstack.io/tutorial-create-a-docker-image-from-a-running-container/

Start up the container

`docker create --name nginx-base -p 80:80 nginx:alpine`

First, we commit the changes with the command:

`docker commit nginx-base`


What this will do is create a new image without a repository or tag. List out the current images with the command:

`docker images`

`docker tag IMAGE_ID nginx-base-container`

There you go, you’ve created a new Docker image from a running container. Let’s stop and remove the original container. To do that, locate the ID of the original with the command:

`docker ps -a`

`docker rm ID -f`

