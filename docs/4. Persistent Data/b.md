# Mapped Folders

One technique for creating persistent data is to share a folder from the host to the container. Start by running the __docker ps__ command and if any containers are running stop them and delete them.

Go to your home directory and create a folder for the container’s persistent data.

````
cd ~
mkdir bb1
````

The __-v__ flag can be used for a few different things, but in this syntax, I’m going to map a host folder called bb1 in the present working directory ($PWD) to a container folder called __Persistent__ in the root directory of the container. 

I used the command

````
sudo docker run -it -v $PWD/bb1:/Persistent --name bb1 busybox
````

I then changed to Persistent as my working directory and created the file __JOR.txt__

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig36.jpg">
<figcaption>Fig 36. File creation.</figcaption>
</figure>

If I use __[ctrl][p] [ctrl][q]__ to exit and then check the contents of the _bb1 directory_ on the host, I can verify my file has been saved.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig37.jpg">
<figcaption>Fig 37. Verify file creation.</figcaption>
</figure>

Now stop and delete the container and verify if the data was in fact persistent.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig38.jpg">
<figcaption>Fig 38. Confirm persistence.</figcaption>
</figure>





