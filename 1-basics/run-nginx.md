## Run NGINX server using docker

From wikipedia:  
- NGINX is a web server that can also be used as a reverse proxy, load balancer, mail proxy and HTTP cache. 
- The software was created by Russian developer Igor Sysoev and publicly released in 2004.
- Nginx is free and open-source software, released under the terms of the 2-clause BSD license. 

### How to run it, using a docker image

- By default, NGINX is listening to port 80
- We'll map this to port 8000 (in my case, Ubuntu has a builtin Apache-2 server listening on port 80)
- We'll use [nginx:alpine](https://hub.docker.com/layers/library/nginx/alpine/images/sha256-22e583d86a570b5a084ed1f27909589de6849977d622cce5d8cfe79df0c5b855?context=explore) tag
- Here's how to run it:  
```
docker run -d -p 8000:80 nginx:alpine
```
- To verify, you can browse to localhost:8000, or use the following curl command:  
```
curl localhost:8000
```

