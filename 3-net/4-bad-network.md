# How to create a bad network

You can specify the range of ip addresses that will be assigned to a docker network.  
Let's try that.

## Making your bad network

- Type the following command:  
```
docker network create -d bridge \
  --subnet 8.8.8.0/24 \
  --ip-range=8.8.8.0/24 \
  --gateway 8.8.8.100 \
  badgoogle
  ```
  This will create a network that will use the 8.8.8.0/24 address range

## Create and test your container

- Create a container that uses that network:  
```
docker run -it --network badgoogle alpine ash
```
- verify your container ip addres:  
```ip a show```
- Try to ping google DNS server:  
```ping 8.8.8.8```