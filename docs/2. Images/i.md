# Sharing Images

There are many places you can share images. For a business I will always share in a private repository. For open-source projects there are many places I could share. 

Docker hub is free, so I'll look at that here. First check the [pricing page](https://www.docker.com/pricing/) to distinguish what is free. You should have created a Docker account.

In Docker hub, you can get all official images, you can also share public or private images. On the free plan, you currently have only one private repo available.

The commands are __docker push HOST:NAME__ and __docker pull HOST:NAME__

This seems very GITHUB like!

## Create a repo

I log into Docker through a browser and go to repositories. I create a new repo called __jortest__ and I take a look through all the menu options and settings. I note the docker command to push something to the repo is __docker push johnoraw/jortest:tagname__

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig44.jpg">
<figcaption>Fig. Docker Repo.</figcaption>
</figure>

Earlier, I created a Python image. __sudo docker images__ show me that it is called _python-docker-server:latest_  

However, my repo is called johnoraw/jortest, I need to rename the image to whatever the repo expects.

````
sudo docker tag python-docker-server:latest johnoraw/jortest:latest
sudo docker images -a
````

The original is still there. The tag command makes a copy rather than renaming.
Next, I need to authenticate to Docker Hub. 
The link to the web browser didn't work (which is a more secure approach).
Using your own credentials...

````
sudo docker login -u johnoraw
````

Then I push the image.

````
docker push johnoraw/jortest:latest
````

When I check online...

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig45.jpg">
<figcaption>Fig. Docker Repo, verify push.</figcaption>
</figure>
