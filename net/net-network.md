# Docker Networking

- List networks:  
**docker network ls**
- List host interfaces:  
**ip link show**
- Create a new bridge network:  
(example)  
**docker network create -d bridge my_bridge**
- List interfaces again:  
**ip link show**  
Do you see the difference?
- Delete the new network:  
**docker network rm \< net id \>**
- List interfaces again.