# docker basic commands

## Basic Commands
- Is docker program installed/running ? (plus more info)  
**docker info**

## Containers

- Run a container:  
**docker run**  
- Use **man docker-run** to get help about this command
- Run a container interactivley (example):  
**docker run -it ubuntu /bin/bash**  
- Run a detached container with a name:  
**docker run --name daemon_dave -d ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"**
- Docker logs:  
**docker logs daemon_dave**  
  or tailed:  
**docker logs -f daemon_dave**  
  or with timestamps:  
**docker logs --tail 0 -tf  daemon_dave**
- Listing containers:   
**docker ps**  
Listing ALL containers (stopped containers as well):  
**docker ps -a**
- See container processes from the outside:  
**docker top daemon_dave**
- See statistics:  
**docker stats daemon_dave**
- Run a non-interactive process inside a container (example):  
**docker exec -d daemon_dave touch /tmp/yuval.dat**
- Run an interactive process inside a container:  
**docker exec -t -i daemon_dave /bin/bash**
- Stop a container:  
**docker stop daemon_dave**
- start a container:  
**docker start daemon_dave**
- Inspect a container:  
**docker inspect daemon_dave**
- Delete a container (should be stopped):  
**docker rm daemon_dave**



## Namespaces

- List networking namespaces:  
**ip netns list**
- Run networking commands inside a networking namespace:  
(Example)  
**sudo ip netns exec cni-24710481-9f5f-ecca-c095-a90a0f35810d  ip a sh**

## Images

