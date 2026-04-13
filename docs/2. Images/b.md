# A first image

It would be useful if we could build our own docker images. We could do this is a very complex way; look at the docker documentation. This walkthrough will be as simple as possible. 

Start by running the __docker ps__ command. If any containers are running stop them and delete them.

Make sure you are in your home directory and create a folder called __baseimage__.

Docker will look for a file called __Dockerfile__, we need to create a blank file with this name.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig3.jpg">
<figcaption>Fig 3. Create Dockerfile.</figcaption>
</figure>

Edit the Dockerfile; I am using nano.

We need to tell Docker what to use as a base image; we will pick Ubuntu.

I used the line

````
FROM ubuntu
````

We need to pass some commands to the image, we use the syntax

````
CMD ["echo", "Ubuntu Container"]
````

Don’t miss any spaces!

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig4.jpg">
<figcaption>Fig 4. First Dockerfile.</figcaption>
</figure>

I saved that and to build it, typed the command 

````
sudo docker build -t ubbase:1.0 .
````

The -t gives a tag to the image and the tag must be lower case.

Don’t forget the full stop, that means “in this directory”.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig5.jpg">
<figcaption>Fig 5. Build Image.</figcaption>
</figure>


Finally, test the image.

````
sudo docker run ubbase:1.0
````
<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig6.jpg">
<figcaption>Fig 6. Run Image.</figcaption>
</figure>


