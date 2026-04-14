# Linux Image

Some of my screenshots below indicate I'm using ub2204. Do not worry about that, this has all ben tested on ub2404.

 I am leaving out the sudo from the following commands, you may need to insert it. Alternatively, add you user name to the sudo group (put your login account name in the <> brackets!) using

````
sudo adduser <username> sudo 
 ````

There are very many prebuilt images on Docker Hub. In ordinary development, we will use these pre-built images.

_Busybox_ is a very small Linux image; type the commands 

````
mkdir busy
cd busy
sudo docker run busybox
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig7.jpg">
<figcaption>Fig 7. Download and run busybox.</figcaption>
</figure>

The image was not present locally, so it was downloaded from Docker Hub. You need to be connected to the Internet for this to work!

Check to see if its running; type the command

````
sudo docker ps
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig8.jpg">
<figcaption>Fig 8. Check running containers.</figcaption>
</figure>

Nothing running! 

Docker runs a container, but if there is no process running in the container, it shuts it back down again. Try the command

````
docker run -it busybox /bin/sh
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig9.jpg">
<figcaption>Fig 9. Running busybox.</figcaption>
</figure>

I start the container again and open a second terminal to check to see if its visible.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig10.jpg">
<figcaption>Fig 10. Check running busybox.</figcaption>
</figure>


To exit from the container terminal and kill the container, type __[ctrl][c]__ or __[ctrl][d]__ or from the shell, __exit__. Containers are ephemeral, once you exit, all your changes are gone.

I can use the command 

````
docker kill 1e3ea51258fd
````
to terminate the process. This sends a signal to the container, we may be able to send a signal to gracefully shut down the process.

I can use the command 

````
docker stop -t 100 1e3ea51258fd 
````

to stop the process in 100 seconds. However, the container is still there! Try the command 

````
docker container ls -a
````
<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig11.jpg">
<figcaption>Fig 11. Check containers.</figcaption>
</figure>

All the containers I have run still show and I can see their original SHA-256 value. 

I may have to type 

````
docker rm 79c98d56a7ab
````
to completely remove the container. 

We could restart a container with 

````
docker rm 8e730d475d28
````
If you want to exit and leave the container running, type __[ctrl][P]__ or __[ctrl][Q]__

Stop and kill all containers before moving on.
