# Lifecycle

In this section, I'm going to work through using the python-docker example. First use the command 

````
docker --help
````

to get a list of all the available Docker commands. Look through them, but you will not need most of them!

- __docker ps__ shows all running containers.
- __docker ps -a__ shows all containers, including stopped ones.
- __docker start _name___ lets me restart a stopped container in a detached mode, it does not block the terminal.

We can run containers in the foreground (attached) or background (detached).

- __docker run _name___ runs a container in the foreground, blocking the terminal. The container is attached, if the container logs data to the terminal, it will appear here.
- __docker run -d  _name___ runs a container in the background, the container is detached.
- __docker container attach _name___ lets me reattach a running container.
- __docker logs _name___ lets me see information that has been printed to the terminal, without reattaching.

If a container needs input from a user, you can __docker run__ with __-it__ flags, to have STDIN and a terminal. Alternatively, you could __docker start__ a container with __-ai__ flags.

## Cleaning up containers

Good practice is to keep everything clean. Containers need to be stopped before deletion.

- __docker stop _name___ stops a container
- __docker rm _name1 name2 name3___ remove three containers.

## Cleaning up images
