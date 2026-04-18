# Basics

We have already seen how to run a container with an interactive terminal and how to force it into the background.

Run the command

````
sudo docker run --name bb1 -itd busybox /bin/sh
````

The bash shell is now running in the background. To get the console back, type

````
sudo docker attach bb1
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig24.jpg">
<figcaption>Fig 24. Reconnect.</figcaption>
</figure>

Use __[ctrl][d]__ to exit.

To run a simple command to the shell of the container, I can use the command

````
sudo docker exec bb1 ls
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig25.jpg">
<figcaption>Fig 25. Execute.</figcaption>
</figure>

