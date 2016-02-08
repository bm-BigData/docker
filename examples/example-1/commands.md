##Commands
1. docker-machne ls
2. docker-machine env [VM-MACHINE-NAME]
3. docker-machine start/stop [VM-MACHINE-NAME]
4. docker run hello-world --Depending on how it was built, an image might run a simple, single command and then exit.
5. docker ps - list all running containers
6. docker ps -a -- list all containers including the stopped ones
7. docker images --The command lists all the images on your local system
8. docker run docker/whalesay cowsay boo-boo
9. docker run docker/whalesay cowsay boo-boo-boo-boo-boo
10. Creating Builds
  1. touch Dockerfile -- refers to the docker file in /examples/example-1/mydockerbuild
    1. FROM docker/whalesay:latest ---The FROM keyword tells Docker which image your image is based on. You are basing your new work on the existing whalesay image.
    2. RUN apt-get -y upgrade & apt-get install -y fortunes ---- The fortunes program has a command that prints out wise sayings for our whale to say. So, the first step is to install it. This line adds the fortune program using the apt-get program
    3. CMD /usr/games/fortune -a | cowsay --- This line tells the fortune program to send its nifty quotes to the cowsay program.
  2. docker build -t docker-whale . ---- build the new image
  3. docker images -- list all images and you should see docker-whale
  
11. 



##Definations
1. <b>Dockerfile</b>
  1. A Dockerfile describes the software that is “baked” into an image. It isn’t just ingredients tho, it can tell the software what    environment to use or what commands to run. Your recipe is going to be very short. 
2. <b>Dummy</b>

##Pictorial Explination
![alt tag](https://docs.docker.com/tutimg/container_explainer.png)
