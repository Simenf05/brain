---
aliases:
  - nat
  - NAT
---

2025-05-26 17:41

Status: #in-writing 
Tags: #communication #networklayer #router #nat #demultiplexing #multiplexing #internet #ip #ipv4

# Network address translation
One important responsibility that happens on the [[Network layer]] is the network address translation. This is often done by home router to separate local or private networks from the rest of the internet. This way we can reuse many ip addresses that dont need to be accessible on the internet. Two examples of local network ip address subnets is 10/8 and 192.168/16. When you see an ip belonging to these subnets its always a local ip address. 
### How NAT works
When the router translates the traffic it will translate a port on a local ip address to one of the ports on the NAT ip address (ip facing the rest of the internet). The NAT router will need to modify all the ip addresses, and ports in the [[Internet protocol|ip]] datagram header to the new ip addresses and ports. With this any response coming to the local ip would end up with the NAT ip, and therefore the NAT router needs to remember what translations it has made so that incoming traffic can be translated to the local network. To remember all the translations the NAT router will use a NAT translation table, so for incoming traffic it will use the table to replace all the ip addresses and ports again. 
### Advantages with NAT
With separating the the ip addresses comes some advantages as in an extra layer of security. In many ways NAT works like a [[firewall]] on your home computer but it also abstracts away the ip from the [[Internet service provider|ISP]]. That way if you want to change [[Internet service provider|ISP]] you only have to change the ip of the NAT router. It also means that you will only ever need one ip from the ISP <sub>(at least for home networks)</sub>.
