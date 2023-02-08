# Docker Networking - default bridge network

Based on [this walkthrough](https://docs.docker.com/network/network-tutorial-standalone/#use-the-default-bridge-network) in the docker material.

## Preparations
- List networks:  
**docker network ls**  
You should see the default bridge network (along with others).
- Run 2 new containers, interactively but detached for now  
(**ash** is the default shell in alpine):  
**docker run -dit --name alpine1 alpine ash**  
**docker run -dit --name alpine2 alpine ash**

## Networking

- Inspect the bridge network to see what containers are connected to it:  
**docker network inspect bridge**
  - you should be able to see an IP gateway for the whole network
  - you should be able to see an IP address for each container
- Attach to a container:  
**docker attach alpine1**
  - Use **ip address sh** to verify ip addressing
  - ping the other container ip address
  - ping google.com
  - ping the default GW

## Cleanup

- Stop and remove containers.
