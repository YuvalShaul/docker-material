# Docker Networking

- List networks:  
**docker network ls**
- List host interfaces:  
**ip link show**
- Create a new bridge network:  
(example)  
**docker network create -d bridge bridge2**
- List interfaces again:  
**ip link show**  
Do you see the difference?

