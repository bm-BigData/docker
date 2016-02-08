##Running nginx
1. create the Dockerfile as showns ine example-2
2. docker build -t nginx-ubuntu . ---- create an image by usinf Dockefile
3. docker run -d -p 80 --name static_web nginx-ubuntu nginx -g "daemon off;"
4. curl http://localhost:32768 (port)
5. docker run -d -p 80:80 --name static_web nginx-ubuntu nginx -g "daemon off;" -- running with container & local port binds to 80
