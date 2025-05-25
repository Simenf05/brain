---
aliases:
  - routing
---

2025-05-20 11:52

Status:
Tags: #communication #it #networklayer #routing #router #packetswitch #packet

# Packet switching
#### Packet switches
The network core consists of devices that forward messages from one end to the other. These are usually referred to as routers or packet switches. A packet switches job is to receive packets from one link, and then to read the headers in that packet to then send it to another link. 

## Circuit switching vs packet switching

The old way of switching is called circuit switching, this method establishes a connection from end to end before transmitting. This way the Service will get a stable connection for the entire duration of the connection. This is not very beneficial for the short burst of transmission that appears on the internet. 

In packet switching the data is split up into packets of data. This way the switches can send data from multiple hosts at the same time while still keeping higher performance. 

### Queuing packets

If a packet switch receives more than it can send at the same time possibly from multiple hosts, then the packet switch will have to queue the packets. If this queue reaches the max capasity then packets will start to drop. This is a risky part of the packet switching model since there is no certanty that the  will be able to receive the pa



## References

Jim Kurose youtube series. 