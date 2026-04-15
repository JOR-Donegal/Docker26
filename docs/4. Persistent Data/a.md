# The problem

When a container is terminated, any data which has changed is lost. There are several different ways data can be stored outside of the container. Start by running the docker ps command and if any containers are running, stop them and delete them.

Try the command 

````
sudo docker run -it --name bb1 busybox
````

You are now at the command prompt of a busybox container and you have full root privilege.

Create a file; I used the command

````
touch JOR.txt
````

and then __|ls -l__. This created a file called JOR.txt and I viewed the directory to confirm.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig31.jpg">
<figcaption>Fig 31. Test file.</figcaption>
</figure>

I can exit form the container by typing [ctrl][p] and then [ctrl][q] and then type docker ps to ensure the container is still running.

````
sudo docker attach bb1
````

Type the command ls -l to make sure the file is still there.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig32.jpg">
<figcaption>Fig 32. Test file (again!).</figcaption>
</figure>

If I exit using [ctrl][d] the process has been stopped and is no longer running. Check this.

Restart the process, check.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig33.jpg">
<figcaption>Fig 33. Check process.</figcaption>
</figure>

Reattach to the container and check to see if the file is there.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig34.jpg">
<figcaption>Fig 34. Check process.</figcaption>
</figure>

Its still there! The data is persistent, the container was shut down but not destroyed.

Exit by typing [ctrl][p] and then [ctrl][q]

Type the commands

````
sudo docker stop bb1
sudo docker rm bb1
````

Type 

````
sudo docker run -it --name bb1 busybox
````

to recreate the container and then type __ls -l__

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig35.jpg">
<figcaption>Fig 35. Listing of new container.</figcaption>
</figure>

The file we created has gone; it was persistent between restarts, but if we remove the container and recreate, all the data in that container is lost. 

Containers can be stopped and deleted, we need to handle any dynamic data accordingly and correctly if we need it to be persistent.


