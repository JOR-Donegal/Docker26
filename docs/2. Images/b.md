# Under the hood

An image could be considered as a template for building containers.

Once you build an image from source code, it is fixed; it is _readonly_. If you make a change to the source code, it will not propagate to an existing image. After you make changes, you need to recreate images using __docker build__.

When I build an image using __docker build__, it caches the result of each instruction. If I make a small change and rebuild, the rebuild is much faster, as docker has cached the result of any build command that has not changed. Each instruction is called a _layer_, the architecture is _layer based_ and the layers are cached. Remember that the image also contains environment information we supplied in the docker file.

You can look inside an image to examine its details by using the command __docker image inspect _name___. Take a look at some of your images. Most images I use are based on Linux.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig42.jpg">
<figcaption>Fig. Image.</figcaption>
</figure>

When we create a container from an image , we add an extra container layer. We do not copy the code, we lock the underlying image as read only. Its a little bit like linked clones? If you examine the size of images and containers, images are big, containers are small.

If we rebuild and layers have not changed, they are taken from cache. Where a change has been made, all layers after that point are rebuilt.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig43.jpg">
<figcaption>Fig. Container.</figcaption>
</figure>

This makes rebuilding efficient. When optimizing Docker code, we may arrange the sequence of steps in the docker file to minimize the number of layers rebuilt.
