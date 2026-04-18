# Shared Volumes

An alternative is to create a volume when we are creating the container. The volume is associated with the container and docker will ensure that the two are bound; docker will not allow you to delete volumes associated with existing containers. 

Start by running the docker ps command and if any containers are running stop them and delete them.

I create a shared data store called __datastore1__ for use by multiple busybox instances. 

Try the command

````
sudo docker create -v /datastore1 --name datastore1 busybox
````

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig39.jpg">
<figcaption>Fig 39. Create datastore.</figcaption>
</figure>

I create a new container called _writer_.

I used the command

````
sudo docker run -it --volumes-from datastore1 --name writer busybox
````

I then changed directory to __datastore1__ and created a dummy file.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig40.jpg">
<figcaption>Fig 40. Create test file.</figcaption>
</figure>

If I spin up another container called _reader_, I can share the volume __datastore1__.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig41.jpg">
<figcaption>Fig 41. Create test file.</figcaption>
</figure>

Note that there is no effective file locking, if two containers access the same file and attempt to write, corruption can be expected. Multiple reads, no problem!




