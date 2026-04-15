# Networking

If you are familiar with VMWare Workstation, you are used to the idea of three network types; NAT, Bridge and Host Only. Bridge is internal to the host.

I do a reboot, I should only have WebServer3 running.

I install the Linux bridge utility; type the command

````
sudo apt-get install bridge-utils
````

I examine the bridge in Linux.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig29.jpg">
<figcaption>Fig 29. Linux bridge.</figcaption>
</figure>

Try the command 

````
sudo docker network ls
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig30.jpg">
<figcaption>Fig 30. Linux bridge.</figcaption>
</figure>

By default, if we run a container, it will use the bridged network.