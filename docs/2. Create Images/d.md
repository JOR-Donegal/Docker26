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

To connect to the outside, I map a port on the container to a port on the host. I run the command

````
sudo docker run -p 80:80 -d nginx
````

and if I browse to the IP address, I get a generic response from the web server. 

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig14.jpg">
<figcaption>Fig 14. Test nginx.</figcaption>
</figure>

Note the port section below, 0.0.0.0:80 maps to the container port 80/tcp.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig15.jpg">
<figcaption>Fig 15. Port for nginx.</figcaption>
</figure>

Now kill the container.

To connect the web service on port 80 of the container to port 8080 of the host, try

````
sudo docker run -p 8080:80 -d nginx
````

Each container is identified by a hash (CONTAINER ID) and a name.

To rename a running container to something meaningful, type the command

````
sudo docker rename practical_chebyshev WebServer1
````

and reverify

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig16.jpg">
<figcaption>Fig 16. Name for nginx.</figcaption>
</figure>

Now kill the container.

It might make more sense to create a meaningful name when creating the container. I could use the command

````
sudo docker run --name WebServer2 -p 81:80 -d nginx
````

Note that I will get an error if I try to use the host's port 80, Webserver1 is already using this. I'm using port 81 and I can check with a browser to make sure this web server is up. 

After a restart, none of these containers will be running.  I could use the command

````
sudo docker run --name WebServer3 --restart=always -p 82:80 -d nginx 
````

to set up a different restart policy. There are several policy alternatives

- no
- failure
- always