# Docker Networking - creating a new bridge network

Based on [this walkthrough](https://docs.docker.com/network/network-tutorial-standalone/#use-the-default-bridge-network) in the docker material.

## A new bridge network and containers

- Create the alpine-net network. You do not need the --driver bridge flag since it’s the default, but this example shows how to specify it:  
**docker network create --driver bridge alpine-net**
- List networks:  
**docker network ls**  
You should see the new bridge network ).
- Run 2 new containers, each one connected to its own network,  
like this:  
**docker run -dit --name alpine1 --network alpine-net alpine ash**  
**docker run -dit --name alpine2 alpine ash**  
(alpine2 is connected to the default bridge)
- Create a 3rd container, connected to both networks:  
**docker run -dit --name alpine3 --network alpine-net alpine ash**  
**docker network connect bridge alpine3**

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
