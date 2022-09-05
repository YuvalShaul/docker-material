# Verify IP addres and hostname

## Run netshoot

nicolaka/netshoot is networking Linux image containing many networking tools.  
  
- Run netshoot:  
**docker run -it nicolaka/netshoot**

## Verify IP

- Verify that your container has an IP address:  
**ip addr sh**
- Verify default GW:  
**ip route**
- Since the default networking in Docker is bridge, you should be able to ping 8.8.8.8 (if you are connected to the Internet),  
**ping 8.8.8.8**
- You can even make sure you are using this gateway, by tracing:  
**traceroute 8.8.8.8**

## DNS

- Run nslookup on netshoot:  
**nslookup**
- Try to resolve a aomain name:  
**googlt.com**  
(notice the address of the DNS server)