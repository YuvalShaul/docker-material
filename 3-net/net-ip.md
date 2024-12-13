## IP and DNS demo
Let's demonstrate some IP and DNS capabilities of containers.

### Preparations

First, let's create a custom network:
```
bashCopydocker network create mynet
```

Now let's create a few containers with different names:
```
docker run -d --network mynet --name web1 nginx
docker run -it --network mynet --name client1 ubuntu bash

# In another terminal, start container 3
docker run -it --network mynet --name client2 ubuntu bash
```

Inside each client container, first install tools:  
```
apt update
apt install -y iputils-ping curl dnsutils
apt install iproute2
```

### Test
```
# From client1 or client2, ping other containers by name:
ping web1
ping client2

# DNS lookup of other containers
nslookup web1
dig web1

# Test web server connectivity
curl web1

# Check DNS configuration
cat /etc/resolv.conf
```

Key points to observe:

- Containers on the same network can resolve each other by name
- Docker provides automatic DNS resolution for container names
- The default DNS server in containers is 127.0.0.11 (Docker's embedded DNS)
- Each container gets its own entry in Docker's DNS
