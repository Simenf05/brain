---
aliases:
  - ip
---

2025-05-26 13:04

Status: #in-writing 
Tags: #communication #networklayer #ip #ipv4 #ipv6 #dns #routing 

# Internet protocol
The internet protocol is the backbone of all communication on the entire internet. Every form of communication is in some way packed into ip datagrams and sent to the link layer. An important thing to remember when talking about the the internet protocol is that it is mainly a way to address the different interfaces on a network. Every interface that is connected to a network has to have an ip address, and routers will use these addresses to route packets through the networks. [[Internet Corporation for Assigned Names and Numbers|ICANN]] is the highest administrator of all the ip addresses in the world, and they distribute them to regional registries that then again redistributes them to [[Internet service provider]]s. For us users are there two versions of ip:
## IPv4
This is the old version of the internet protocol, and in this version every [[ip address]] is 32-bits or 4 bytes. To cover every device on a network with the size of the entire internet you would need way more than this and this is the reason we need technologies that divide up all the addresses. To do this a technique called [[#sub netting]] is used. 
### The IPv4 datagram format
This is the structure of the ip datagram:
<img src="./IP-datagram-format.png" alt="" width="400"/>
The first part of the header is always the version, and this is so that any program reading the datagram will know what the other fields correspond to. 
We have both the header length, and the datagram length since the header and payload has variable length. The normal size of datagrams is 1500 bytes, this allows them to fit into a payload of the [[ethernet]] [[link layer]] frame. 
The "type of service" field has been used for multiple things over the years, but the most important use today is the explicit congestion notification (ECN) bit. This bit is flipped by routers and used by the [[transport layer]] to avoid [[Congestion control|congestion]]. 
Time to live is decreased once for every router the datagram passes by. If it reaches zero the datagram will not be sent. This is to avoid zombie datagrams that never reach a destination. 
Upper layer indicates what transport protocol is used. And header checksum is self explanatory. 
After this is the ip addresses and any options.
#### Overhead
With this we get at least 40 bytes of overhead for [[TCP]]/IP.
20 bytes from tcp + 20 bytes from ip + app layer overhead
### Sub netting
#### Classless InterDomain Routing (CIDR)
### [[Network address translation]]


## IPv6



## How to get an [[ip address]]

### Set ip on host


### Dynamic Host Configuration Protocol (DHCP)
[[Dynamic Host Configuration Protocol]]
