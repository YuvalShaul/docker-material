# Docker Volume

## Create a named volume

- Create a **named** docker volume:  
(example)  
**docker volume create --name  vol1**
- Use **sudo ls /var/lib/docker/volumes** to see where your volume lives on the host.
- List docker volumes:  
**docker volume ls**


## Connect a container to the volume

- Mount the named volume on first container:  
**docker run -it --name alpine1 -v vol1:/volpath1 alpine**
- cd (inside the container) into the /extvol1, create a file (e.g: msg.txt) with some content:  
**echo hello > msg.txt**
- Exit the container, and view the file:  
**sudo cat /var/lib/docker/volumes/vol1/_data/msg.txt**  
- Delete the container and make sure that the volume is still there (also the file)

## Create a container + volume

- Cleanup:
  - remove all containers (that have mounted a volume)
  - remove all volumes that are not used by a container:  
  **docker volume prune**
- Verify the list of volumes:  
**docker volume ls**
- run a container, specify just a mount point, and get an anonymous container:  
**docker run -it -v /containerpath --name alpine2 alpine**
- Verify the creation of a new anonymous volume:  
**docker volume ls*
