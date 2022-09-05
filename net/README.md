# Docker Networking

## Stop Apache 2 

If it is running, stop Apache 2:  
**systemctl stop apached**


## NGINX

- Run NGINX and expose port 8080 on the host:  
**docker run  -d -p 8080:80 nginx**
- Test:  
**curl localhost:8080**