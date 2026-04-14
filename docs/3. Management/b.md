# Performance 

Linux has a command top which allows us to see the processes which are running. We can do the same in containers. I tried the command 

````
sudo docker top WebServer3
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig26.jpg">
<figcaption>Fig 26. Top in a container.</figcaption>
</figure>

Another useful command is 

````
sudo docker stats
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig27.jpg">
<figcaption>Fig 27. Stats in a container.</figcaption>
</figure>

Consider the memory usage of each container and for contrast, see how much memory your VM is using the Linux command __free__.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig28.jpg">
<figcaption>Fig 28. Memory from the host OS.</figcaption>
</figure>

Now you can really appreciate how lightweight the containers are.

To really get into detail, I could type 

````
sudo docker inspect WebServer3
````

I will let you go through the output to see the detail available. This will scroll right off the screen with many pages of JSON. Its worth going through to see what kind of data is maintained. Down at the end is all the network information.