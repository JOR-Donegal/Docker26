# Python Container

If you check DockerHub, you will see that there are base images for Python.

You installed gunicorn way back at the start of these exercises. Check now to make sure you did so!

I change directory to __~/Docker__ and I download a simple Docker Python example file from Github.

````
git clone https://github.com/docker/python-docker
````

I take a look at the contents of the _python-docker_ directory.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig17.jpg">
<figcaption>Fig 17. Directory.</figcaption>
</figure>

Using __more__, look into each file and understand!

Use the __more__ command to look at the contents of each file. Do some background reading to understand __Flask__, but it is a small and lightweight Python web framework very commonly used. 

Now I have an application, I need to containerize it. My working directory is _~/Docker/python-docker_, I run the command 

````
docker init
````
which gives me a wizard-like prompt

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig18.jpg">
<figcaption>Fig 18. Init prompt.</figcaption>
</figure>

 I use all the defaults.

 <figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig19.jpg">
<figcaption>Fig 19. Init prompt completed.</figcaption>
</figure>

I now have the following files.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig20.jpg">
<figcaption>Fig 20. Files, post init.</figcaption>
</figure>

I run 

````
gunicorn -v
````

to see what version of the gunicorn web server I have.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig21.jpg">
<figcaption>Fig 21. Gunicorn version.</figcaption>
</figure>

I edit _requirements.txt_ and add the line

````
gunicorn==20.1.0
````

I then run the container using

````
sudo docker compose up --build
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig22.jpg">
<figcaption>Fig 22. Build.</figcaption>
</figure>

I open a web browser to test

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig23.jpg">
<figcaption>Fig 23. Test.</figcaption>
</figure>


