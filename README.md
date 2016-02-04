# What is a docker?

Docker solves many of the same problem that a VM solves, plus some other that VMs could solve if they didn’t were so resource intensive. Here are some of the things that Docker can deal with:

    Isolating an application dependencies

    Creating an application image and replicating it

    Creating ready to start applications that are easily distributable

    Allowing easy and fast scalation of instances

    Testing out applications and disposing them afterwards

# Docker Main Concepts

The two most important entities in Docker are images and containers. Aside from those, links and volumes are also important. Let’s start with images.

##Images
Images on Docker are like the snapshot of a virtual machine, but way more lightweight, way way way more lightweight (more on the next section). Images have an unique ID, and an unique human-readable name and tag pair. Images can be called, for example, ubuntu:latest, ubuntu:precise, django:1.6, django:1.7, etc. There are several ways to create an image on Docker, most of them rely on creating an new image based on an already existing image

##Containers
Now onto containers. From images you can create containers, this is the equivalent of creating a VM from a snapshot, but way more lightweight. Containers are the ones that run stuff.
Let use an example, you could download an image of ubuntu (there is a public repository of images called the docker registry), modify it by installing Gunicorn and your Django app with all its dependencies, and then create a container from that image that runs your app when it starts.

![alt tag](https://github.com/bm-BigData/docker/blob/master/images/containers-1.png)

Containers, like VMs, are isolated (with one little caveat that I’ll discuss later). They also have an unique ID and a unique human-readable name. It’s necessary for containers to expose services, so Docker allows you to expose specific ports of a container.

![alt tag](https://github.com/bm-BigData/docker/blob/master/images/containers-2.png)

Containers have one big difference that separate them from VMs, they are designed to run a single process, they don’t simulate well a complete environment. 
