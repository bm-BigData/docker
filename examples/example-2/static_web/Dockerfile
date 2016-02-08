# Version: 0.0.1
From ubuntu:14.04
MAINTAINER Buland Malik "bulandaltaf@gamil:.com"

# Keep upstart from complaining 
RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -sf /bin/true /sbin/initctl

# Let the conatiner know that there is no tty 
ENV DEBIAN_FRONTEND noninteractive 

# Update and install some useful apts 
RUN apt-get update

# Avoid ERROR: invoke-rc.d: policy-rc.d denied execution of start. 
RUN echo "#!/bin/sh\nexit 0" > /usr/sbin/policy-rc.d
RUN apt-get upgrade -y

# install nginx
RUN apt-get install -y nginx

# set the cotent that we want to return
RUN echo "Hi, Welcome to your container" > /usr/share/nginx/html/index.html

# expose port 80
EXPOSE 80

# This is important that setting uid to 1000 if you are using Mac and need to mount a location from host. 
# Cause other users you created in container don't have the permisstion to write in mounted volumne except user docker(1000) in boot2docker, and you can't do anything about it. 
RUN useradd -u 1000 webapps
