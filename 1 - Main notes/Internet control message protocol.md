---
aliases:
  - icmp
  - ICMP
---

2025-05-27 14:18

Status:
Tags: #communication #networklayer #protocol #controlplane 

# Internet control message protocol
The Internet control message protocol is used by hosts and routers to communicate on the [[Network layer|network layer]] with network specific information. With ICMP it will package the payload directly into the [[Internet protocol|IP datagram]], and this means no [[Reliable data transfer|rdt]]. 
### ICMP message structure 
The first byte of the ICMP message is the type of message, the second byte is the code and after this it is 2 bytes for the checksum. The next 8 bytes after this contains the description for the ICMP message. This can be [[time to live|TTL]] expired or other networking maintenance messages.  
### Traceroute
With the traceroute command on unix-like systems we can identify the ip addresses of the router between to ip addresses. This is done by sending [[User datagram protocol|udp]] datagrams with [[time to live]] set to 1, and then when the router expires the [[time to live]] it might send back the ICMP message. This way by incrementing the time to live on [[User datagram protocol|udp]] datagrams we can track the route taken by traffic over the internet. 