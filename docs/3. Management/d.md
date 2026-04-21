# Cheat Sheet

In this section, I'm going to work through using the python-docker example. First use the command 

````
docker --help
````

to get a list of all the available Docker commands. Look through them, but you will not need most of them!

- __docker ps__ shows all running containers.
- __docker ps -a__ shows all containers, including stopped ones.
- __docker start _name___ lets me restart a stopped container in a detached mode, it does not block the terminal.

We can run containers in the foreground (attached) or background (detached).

## Dockerize an application

Where I have an application, for example in Python, I can run __docker init__ to create the Dockerfile and any required assts.

## Containers

- __sudo docker ps__ will show running container processes
- __sudo docker container ls -a__ will show all containers


## Building containers

Make sure to include the dot below, to build from the docker file in the working folder.

- __docker build .__

You can assign a name to an image using a name and a tag. You can use the name to specify the general image type and the tag to assign something specific, like a version. If I write a serial comms image container with a specific version of Python, this could be useful.

- __docker build -t serialcomms:3.12 .__

## Running containers.

- __docker run _name___ runs a container in the foreground, blocking the terminal. The container is attached, if the container logs data to the terminal, it will appear here.
- __docker run -d  _name___ runs a container in the background, the container is detached.
- __docker container attach _name___ lets me reattach a running container.
- __docker logs _name___ lets me see information that has been printed to the terminal, without reattaching.

If a container needs input from a user, you can __docker run__ with __-it__ flags, to have STDIN and a terminal. Alternatively, you could __docker start__ a container with __-ai__ flags.

Another useful option is __--rm__, which removes the container when it finishes running.

You can copy files to and from a running container using __docker cp _source destination___.

Automatic container names are long and unwieldy. It makes more sense to name a container as you create it. __--name _name___ allows us to create a container with a meaningful name.

## Cleaning up containers

Good practice is to keep everything clean. Containers need to be stopped before deletion.

- __docker kill _name___ stops a container
- __docker stop -t 10 _name___ stops a container gracefully after 10 seconds
- __docker rm _name1 name2 name3___ removes three containers.

## Images
- __sudo docker pull _image___ will pull an image from Docker Hub.
- __sudo docker run _image___ will will create a running container from this image.



## Cleaning up images

- __docker _images___ lists all our existing images.

If a container is using an image, you cannot delete the image.

- __docker images prune -a__ will remove all unused images.

- __docker rmi _name___ removes a specific image, deleting all layers.

