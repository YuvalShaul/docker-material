# Docker bind storage

Directly run an alpine container with a bind to a directory.  
This directory should already exist on the host machine.  

## Old Syntax
- We have a directory called target already created.
- Create a container and bind the target directory to /app directory inside the container:  
**docker run -it -v /home/yuval/Documents/docker-material/4-storage/target:/app --name alpine1 alpine**
- To check:  
cd into /app and create a file called hello.msg:  
**cd /app**  
**echo hello > hello.msg**
- Exit from the container, and check the file:  
**cd target**  
**cat hello.msg**


## New Syntax

- We do the same thing using **--mount**
- Delete the previous container
- Run:  
**docker run  -it --mount type=bind,source="$(pwd)"/target,target=/app   busybox**
