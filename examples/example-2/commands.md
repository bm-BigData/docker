##RUnning nginx
1. docker run -d -p 80 --name static_web bmalik_ubuntu nginx -g "daemon off;"
2. curl http://localhost:32768 (port)
3. docker run -d -p 80:80 --name static_web bmalik_ubuntu nginx -g "daemon off;"
