# Introduction

!!! abstract "Containers and Docker"

_Containers_ revolutionized software development by providing a lightweight, efficient, and portable solution for packaging applications and their dependencies, running under a single operating system kernel. They are thus more lightweight than Virtual Machines (VMs). VMs can also provide isolated, independent application environments, but they have considerable overhead compared to containers. A container only holds the minimum it actually requires.

A container encapsulates an application and all its required libraries, binaries, and configuration files into a standardized unit that can run seamlessly across different computing environments. Each container is fully independent of other containers and applications. This isolation ensures consistency and reproducibility, allowing developers to build, deploy, and scale applications with ease. 

Containers are flexible, enabling rapid development, continuous integration, and deployment workflows. They promote a microservices architecture, facilitating modular development and simplifying maintenance and updates. Developers can achieve greater efficiency, agility, and consistency in software delivery, making it particularly suitable for DevOps.

The same container with all its dependencies will always give you the same result, with the same underlying library versions, it just works. There are no issues moving between development and production environments or between developers. 

_Docker_ is perhaps the best known platform as a service (PaaS) container ecosystem providing OS level virtualization. Linux has built-in container support and on top of this, the Docker Engine is installed.

A container is created from a configuration file, or you can create an image to create containers.

The big picture...containers are a way to achieve a micro-services architecture, where each component is separate, independent, may be written in a different language, etc. Teams can develop components independently of each other. Do some background reading on microservices now.