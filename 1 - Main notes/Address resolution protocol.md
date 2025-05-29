---
aliases:
  - arp
  - ARP
---

2025-05-29 15:42

Status: #in-writing 
Tags: #communication #protocol #it #linklayer #mac-address #ip #arp

# Address resolution protocol
The address resolution protocol is used for getting the MAC address from just knowing the [[IP]] address. For the purpose of remembering old MAC addresses there is a table for every interface with a IP to MAC lookup plus a [[time to live]]. This table is called the ARP table. If the node has an IP that it not in the ARP table then the node uses the address resolution protocol, and will put the MAC it gets in the ARP table after that. 
## ARP flow
To start off the node that want to find the ip address will transmit the ip on the FF:FF:FF:FF:FF:FF 



