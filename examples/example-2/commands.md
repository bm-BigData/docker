##Running nginx
1. create the Dockerfile as showns ine example-2
2. docker build -t nginx-ubuntu . ---- create an image by usinf Dockefile
3. docker run -d -p 80 --name static_web nginx-ubuntu nginx -g "daemon off;"
4. curl http://localhost:32768 (port)
5. docker run -d -p 80:80 --name static_web nginx-ubuntu nginx -g "daemon off;" -- running with container & local port binds to 80
  1. -p specifies the port we are exposing in the format of -p local-machine-port:internal-container-port. In this case we are mapping Port 80 in the container to Port 80 on the server 
6. docker attach <i>container-name </i>
