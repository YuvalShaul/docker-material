# docker first run

- Start by running a very old Ubuntu **docker** image:  
**docker run -it  ubuntu:10.04 /bin/bash**
- Ubuntu 10.04 (Lucid Lynx) is an image from 29 April 2010.  
Let's compare bash of that time to the one in a current release (I am using 22.04 now - Feb 2023):  
**ls -l /bin/bash**  
(you should run this in both places)
- try to run **vin** editor (not the older **vi**)
- Now install it:  
**apt-get update**  
**apt-get install -y vim**  
(try running it again)
- Look at **ALL** current running processes inside the container:  
**ps -e**  
(maybe compare to the same on your own ubuntu)
- Look at interfaces and ip addresses inside the container:  
**ip link show**  
**ip addr show**  
- **MAKE SURE YOU CONVINCE YOURSELF THAT THIS IS NOT A TRUE OS RUNNING:**
  - run **uname -a**  on your ubuntu
  - run **uname -a**  inside the container
OK?

