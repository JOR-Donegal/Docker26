# Web Server

Now we will download a web server container as used in many commercial applications.

````
sudo docker pull nginx
````

If I type 

````
sudo docker run nginx
````

the console freezes; this container runs in the foreground. If I check from the other console with the command

````
sudo docker ps
````

command, I can see that __nginx__ is running. 

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig12.jpg">
<figcaption>Fig 12. Check nginx.</figcaption>
</figure>

Exit from the nginx container using __[ctrl][c]__.

If I type  

````
sudo docker run -d nginx
````
then the container is forced to run in the background; it displays a SHA-256 hash of the container and then returns us to the command prompt.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig13.jpg">
<figcaption>Fig 13. Run nginx in background.</figcaption>
</figure>
