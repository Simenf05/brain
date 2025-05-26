2025-05-25 15:02

Status:
Tags: #communication #networklayer #it #ip-address #ip #ipv4 #ipv6 #nat #router #dhcp

# Networking layer
The networking layer consists of two main parts: 
- The data plane
- The control plane

### The data plane 
In the networking layer the data plane is defined as the actions that are done on a per-router basis. This means forwarding packets, and to do this it has to read from the IP headers and determine where to send the packet. More about that [[The data plane (networking)|here]].

### The control plane 
The other responsibility of the networking layer is to provide a best effort attempt to give end-to-end forwarding of the packets. Therefore we have the control plane which determines the overall [[Packet switching|routing]] of the packets. Packets will route through many [[Router|routers]] and there needs to be a clear path between all the routers that make the packet arrive to its destination. More about this [[The control plane (networking)|here]].





