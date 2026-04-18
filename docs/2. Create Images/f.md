# Finally

An image could be considered as a template for building containers.

Once you build an image from source code, it is fixed; it is _readonly_. If you make a change to the source code, it will not propagate to an existing image. After you make changes, you need to recreate images using __docker build__.

When I build an image using __docker build__, it caches the result of each instruction. If I make a small change and rebuild, the rebuild is much faster, as docker has cached the result of any build command that has not changed. Each instruction is called a _layer_, the architecture is _layer based_ and the layers are cached.

<figure>
<img src = "https://jor-donegal.github.io/Docker26/images/fig42.jpg">
<figcaption>Fig . Image.</figcaption>
</figure>

