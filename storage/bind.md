# Docker bind storage

- Directly run an Ubuntu image with a bind to a directory.  
This directory should already exist on the host machine.  
It will be call /app in the container.  
**docker run  -it  --mount type=bind,source="$(pwd)"/target,target=/app   busybox**
- Now, cd into /app and create a file called hello.msg:  
**cd /app**  
**echo hello > hello.msg**
- Exit from the container, and check the file:  
**cd target**  
**cat hello.msg**
