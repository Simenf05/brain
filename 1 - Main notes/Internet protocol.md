---
aliases:
  - ip
  - IP
---

2025-05-26 13:04

Status: #in-writing 
Tags: #communication #networklayer #ip #ipv4 #ipv6 #dns #routing #protocol

# Internet protocol
The internet protocol is the backbone of all communication on the entire internet. Every form of communication is in some way packed into ip datagrams and sent to the link layer. An important thing to remember when talking about the the internet protocol is that it is mainly a way to address the different interfaces on a network. Every interface that is connected to a network has to have an ip address, and routers will use these addresses to route packets through the networks. [[Internet Corporation for Assigned Names and Numbers|ICANN]] is the highest administrator of all the ip addresses in the world, and they distribute them to regional registries that then again redistributes them to [[Internet service provider]]s. For us users are there two versions of ip:
## IPv4
This is the old version of the internet protocol, and in this version every [[ip address]] is 32-bits or 4 bytes. To cover every device on a network with the size of the entire internet you would need way more than this and this is the reason we need technologies that divide up all the addresses. Each part of the network that can see each other without going through a [[router]] is called a [[#subnets|subnet]]. 
### The IPv4 datagram format
This is the structure of the ip datagram:
<img src="./ipv4-datagram-format.png" alt="" width="400"/>
The first part of the header is always the version, and this is so that any program reading the datagram will know what the other fields correspond to. 
We have both the header length, and the datagram length since the header and payload has variable length. The normal size of datagrams is 1500 bytes, this allows them to fit into a payload of the [[ethernet]] [[link layer]] frame. 
The "type of service" field has been used for multiple things over the years, but the most important use today is the explicit congestion notification (ECN) bit. This bit is flipped by routers and used by the [[transport layer]] to avoid [[Congestion control|congestion]]. 
Time to live is decreased once for every router the datagram passes by. If it reaches zero the datagram will not be sent. This is to avoid zombie datagrams that never reach a destination. 
Upper layer indicates what transport protocol is used. And header checksum is self explanatory. 
After this is the ip addresses and any options.
#### Overhead
With this we get at least 40 bytes of overhead for [[Transmission control protocol|TCP]]/[[Internet protocol|IP]].
20 bytes from tcp + 20 bytes from ip + app layer overhead
### Subnets
A subnet is defined as interfaces on a network that can physically communicate without needing to go through a [[router]]. The way this is standardized is by dividing up the ip address into two parts, host part and subnet part. All devices on the same subnet should share the same subnet part and be different on the host part. When we describe subnets we often describe it using the CIDR notation. 
#### Classless InterDomain Routing (CIDR)
The CIDR notation means that the first x bits behind the / is the subnet part of every ip on that subnet.  For example 223.1.1.0/24 would mean a subnet with every ip address on the form **223.1.1.x**. The rest of the ip address would be the host specific of the ip address. With this notation the values that corresponds to 0 might be omitted, meaning 10.0.0.0/8 = 10/8. An important observation is that the smaller the subnet part of the ip the bigger the subnet is, with a /24 network there is only $2^8$ possible addresses on the range, and some of them are even reserved. On every network the 255.255.255.255 ip is reserved for broadcasting to the entire network, and 0.0.0.0 ip refers to "this" network. [Full list of reserved ip addresses](https://en.wikipedia.org/wiki/Reserved_IP_addresses).
For routing the subnets will always use [[Router#longest prefix matching]] to match the ip with the right subnet. That way we always know where to route a ip address in a network. 
### [[Network address translation]]
The network address translation is important because it allows us to reuse many ip addresses. Although [[Network address translation|NAT]] is great, it is only used with [[#IPv4]] and it is part of why many dont like IPv4. In some cases it over complicates the process of having connection in and out of the local network. Even though [[Network address translation|NAT]] is not the purest form of networking my toilet still will not need an unique ip address accessible from the entire internet. Read more about NAT on [[Network address translation|this]] page.
## IPv6
The initial motivation for developing IPv6 started because we rapidly used up all the [[#IPv4]] ip addresses, and therefore we needed a bigger range of addresses. With this the idea for 128-bit addresses came into play. 128 bits would allow for $2^{128}$ addresses, and this is most likely enough for the rest of humankind. The IPv6 would also be a way to learn from past mistakes and make a better standard for the internet. One of the mistakes that was made by the header of [[#IPv4]] is that the header checksum has to be calculated for each router. All of this is different motivations for the newer and better IPv6.
### IPv6 datagram format
<img src="./ipv6-datagram-format.png" alt="" width="400"/>
The only new header field is the flow label field, and that is used for indicating that datagrams are in the same flow. A flow is not well defined, so it is up for implementation to define. 
### Transitioning from IPv4 to IPv6
The transition is well in action and most services on the internet use IPv6 nowadays. But when we still have some parts of the network that dont support IPv6 a technique called tunneling might be used.
#### Tunneling
If two IPv6/4 routers are transmitting a IPv6 datagram, but have a network of IPv4 only routers between them they might use tunneling. In action it works by wrapping the IPv6 datagram in a IPv4 datagram and sending it. This way routers that support both versions can translate between the different versions. 
On the first router that needs to translate, there will be a row on the forwarding table indicating that the correct forwarding to get to the other IPv6/4 router is by tunneling the datagram through the IPv4 network. To tunnel the datagram it must make a new IPv4 datagram with the source as itself, and the destination as the second IPv6/4 router. Then it will have the payload as the IPv6 datagram and send it to the IPv4 network. 





## How to get an [[ip address]]


### Set ip on host





### Dynamic Host Configuration Protocol (DHCP)
[[Dynamic Host Configuration Protocol]]
