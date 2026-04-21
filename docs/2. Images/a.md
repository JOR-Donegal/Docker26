# Images

We need to understand the term _image_. We can create a master copy of an operating system that we want to be able to run, this is an image. If we go to hub.docker.com and look at the templates available, there are many.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig1.png">
<figcaption>Fig 1. The docker hub.</figcaption>
</figure>

I can also check locally, to which images I have downloaded using __sudo docker images__.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig2.png">
<figcaption>Fig 2. The docker hub.</figcaption>
</figure>

It is from these images that containers are created.

## Containers

A _container_ is a unit of software isolated from the host and OS from where it is run. Containers have everything the software needs to run, including a base operating system. Docker's own definition is

"A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another."

Containers are created from images, images are the templates, containers are the executing code. A single image can be used to create many containers.