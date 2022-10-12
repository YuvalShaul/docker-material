# Docker Volume

- Create a docker volume:  
(example)  
**docker volume create --name  vol1 --opt size=100m**  
The --opt part starts options that are sent to the driver  
Use **sudo ls /var/lib/docker/volumes** to see where your volume lives on the host.
- List docker volumes:  
**docker volume ls**
- Mount this volume:  
**docker run -it  -v vol1:/extvol1 ubuntu**
- cd into the /extvol1, create a file (e.g: msg.txt) with some content.
- Exit the container, and view the file:  
**sudo cat /var/lib/docker/volumes/vol1/_data/msg.txt**  
- Delete the container and make sure that the volume is still there.