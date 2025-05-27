---
aliases:
  - the control plane
---

2025-05-25 15:41

Status: #in-writing 
Tags: #communication #networklayer #ip #ipv4 #ipv6 #it #technology #packetswitching 

# The control plane (networking)
The control plane is part of the [[networking layer]] and it is responsible for the big picture of the network. While [[The data plane (networking)|the data plane]] has the responsibility to forward packets from one link on a router to the next, the control plane is making sure that it forwards it to the right link. This means that it is the control planes responsibility to set the [[Router#Forwarding table|forwarding tables]] of the routers in a network, and this can often be done with [[Software defined network]] (SDN) or computed on the network itself. The computation is done with different [[Routing algorithms|routing alogrithms]]. 
### Network management 
The control plane also has some important protocols relating to the management of the network, and this includes [[Internet control message protocol|ICMP]], [[SNMP]] and [[NETCONFIG]]. 