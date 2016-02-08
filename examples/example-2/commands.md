##Running nginx
1. docker-machine create -d virtualbox fdocker --- create new virtual machine fdocker
2. docker-machine ssh fdocker - connect to fdocker vm
2. create the Dockerfile as showns ine example-2
2. docker build -t nginx-ubuntu . ---- create an image by usinf Dockefile
3. docker run -d -p 80 --name static_web nginx-ubuntu nginx -g "daemon off;"
4. curl http://localhost:32768 (port)
5. docker run -d -p 80:80 --name static_web nginx-ubuntu nginx -g "daemon off;" -- running with container & local port binds to 80
  1. -p specifies the port we are exposing in the format of -p local-machine-port:internal-container-port. In this case we are mapping Port 80 in the container to Port 80 on the server 
6. docker attach <i>container-name </i>
7. docker attach --sig-proxy=false <i>container-name </i>
7. docker inspect --format '{{ .NetworkSettings.IPAddress }}' static_web
8. docker inspect static_web


##Another approach
1. docker pull nginx
2. docker run --name docker-nginx -p 80:80 nginx
3. 

##Another Approach
1. docker run -i -t -p 80:80 ubuntu /bin/bash ----- Using docker's RUN command, we will begin with creating a new container based on the Ubuntu image. We are going to attach a terminal to it using the “-t” flag.
2. echo "deb http://archive.ubuntu.com/ubuntu/ raring main universe" >> /etc/apt/sources.list ----In order to install Nginx and the tools we are going to need for the process, the relevant application repository must be available for downloads. Let's append Ubuntu's universe to the default list of the base image.
3. apt-get update ---Update the list with the newly added source.
4. apt-get install -y nano \
                   wget \
                   dialog \
                   net-tools  
  1. Before we proceed to install Nginx, there are some tools we should have installed such as nano - just in case.
5. apt-get install -y nginx ---Installing Nginx


##Tutorials
1. https://www.digitalocean.com/community/tutorials/docker-explained-how-to-containerize-and-use-nginx-as-a-proxy
