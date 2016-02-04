##Commands
1. docker-machine ls
2. docker-machine active -- shows which vm is active
3. docker-machine start fdocker ---running fdocker docker vm
4. docker-machine env fdocker
3. docker pull ubuntu:latest --lets download an image from the public registry 
4. docker images --list of images
5. docker run --rm -ti ubuntu /bin/bash --create a container from that image

Quick rundown of what you did on that last command:
    --rm: tells Docker to remove the container as soon as the process is running exits. Good for making tests and avoiding clutter

    -ti: tell Docker to allocate a pseudo tty and put me on interactive mode. This is for entering the container and is good for rapid prototyping and playing around, but for production containers you will not be turning these flags on

    ubuntu: this is the image we're basing the container on

    /bin/bash: the command to run, and since we started on interactive mode, it gives us a prompt to the container

6.  docker run -d ubuntu ping 8.8.8.8 ---run a container on the background
7.  docker ps ---check out what our container is up to
$> docker ps
CONTAINER ID IMAGE         COMMAND         CREATED        STATUS        PORTS  NAMES
31c68e9c09a0 ubuntu:latest "ping 8.8.8.8"  2 minutes ago  Up 2 minutes         loving_mcclintock

8.  docker exec -ti loving_mcclintock /bin/bash ---check inside the container to see what's happening
What we just did is to execute a program inside the container, in this case the program was /bin/bash. The flags -ti serves the same purpose as in docker run, so it just placed us inside a shell in the container.
