---
aliases:
  - packet switch
---
2025-05-25 15:23

Status: #in-writing 
Tags: #networklayer #communication #it #packetswitch #router #forwarding #routing #packet

# Router
The router is the most fundamental part of every network on the internet. It serves as the final piece that connects and redirects [[link (network layer)|links]] in the network. A router often has many input and output links connected to it, and can redirect between them. When a router redirects one input link to another output link it is called forwarding, and when a packet travels through the network on many routers it is called [[Packet switching|routing]]. 
### Forwarding
The action of connecting one link to another is called forwarding. What link to forward to is determined by the forwarding table. There exists two main types of forwarding tables, [[#destination based forwarding]] and [[#longest prefix matching]]. The next part of the router is the part responsible for connecting the input link to the output link. This is done in whats called a [[#switching fabric]] and this can be done in multiple ways.
#### Forwarding table
##### Destination based forwarding
In this type of forwarding table the destination is determined by a set of ranges in the table. Every output link will have a corresponding range of ip ranges to match for. 

| Destination address Range                                                                         | IP link interface<br> |
| ------------------------------------------------------------------------------------------------- | --------------------- |
| ```11001000 00010111 00010000 00000000```<br>through<br>```11001000 00010111 00011111 11111111``` | 1                     |
| ```11001000 00010111 11110000 00000000```<br>through<br>```11001000 00010111 11111111 11111111``` | 2                     |
| otherwise                                                                                         | 3                     |

The problem with this can be that it might get complicated when certain links needs extra configuration. And that is why we have longest prefix matching.
###### Longest prefix matching
With longest prefix matching the last part of the table ip ranges will instead be wildcards. In practice this means that any ip with the same start can match on a link. But this is where the longest prefix matching is relevant. Because it will always match with the table row that has the least wildcards. This way the links can be as specific as the need to be but also as generic as they need. And it will always match the right link. 

| Longest prefix matching                   | IP link interface<br> |
| ----------------------------------------- | --------------------- |
| ```11001000 00010111 00010000 00******``` | 1                     |
| ```11001000 00010111 00010000 ********``` | 2                     |
| ```******** ******** ******** ********``` | 3                     |
In this example the ip ```11001000 00010111 00010000 00110011``` would be sent to the first link since it has the longest prefix and matches. For every ip that does not match either link 1 or link 2 would be forwarded to link 3. 
For the longest prefix matching it is often used a #technology called ternary content addressable memory (TCAM) , which can retrieve the link from the table in one [[clock cycle]] no matter how big the table is. 
#### Generalized forwarding
Generalized forwarding is a newer way of designing the forwarding tables for routers. With this approach we generalize the [[#forwarding table]]. That way we instead of only looking at the destination ip address to determining where to forward the datagram, we also allow other fields in the header to impact the forwarding. The action that is performed on the datagram is also generalized to allow for more nuance. 
All action s that can be performed on the datagram:
- drop
- modify
- forward
- send to controller
This way the routers can be configured to respond differently to different types of datagrams, and for example drop everything from certain addresses. This can be useful for maintenance and logging. OpenFlow is a standard of the generalized forwarding approach and with it routers can match actions with headers from [[link layer]], [[networking layer]] and the [[transport layer]].
#### Switching fabric
The switching fabric is the part that links the input link and output link. This is done by moving the packet from one link to the other. Switching fabric has a switching rate that determines how much it manages to switch at a certain time. If there is N ports and they each have a rate of R, then the optimal switching rate would be NR. But this might be expensive and therefore cheaper routers might not have this good switching rate. If the switching rate is not sufficient to handle the amount of traffic, then the input links will start to build up queues, and this is referred to as input port queuing. There exists three main ways for the switching fabric and they each have different levels of switching rates. 
##### Memory switching
In memory switching there is a piece of memory that the packets are loaded into, and then a cpu processes the packet and decides what output link to send it to. This is the oldest and slowest type of switching fabric. 
##### Bus switching
Bus switching is based on having a shared bus connection that connects all the input and output links. This way we dont have to move the datagram into memory and save a lot of time. While this is still faster then memory switching, it will still be limited by the bandwidth of the bus. 
##### Interconnection network switching
With interconnection networks the idea is that every input should be connected to every output on a specified link. We can have grids where every link is connected to every output link in a $N*N$ format. This works, but a more common way of designing it is multistage switches. This is done by having intermediate switches in the switch. That way the complexity will not scale by $N²$.
One other upside of the fragmented approach is that multistage switching can get better use out of parallelism. Because it can split up the datagram and send them over different switches to then reassemble them at the output link. 
### Output port queuing 
If the switching fabric is sending at a rate of NR to one link but that link only has a transmission rate of R then there has to be some queuing. This is where packets will have to be dropped and different drop and scheduling policies take action.  
#### Buffer management 
There is many ways of dealing with too much input in the buffer without the output link being able to transmit fast enough. When the buffer is full and all the new packets arriving are dropped is called **tail dropping**. Another policy for dropping can be based on priority of the packets. Some packets might have a higher priority, and then the low priority packets re dropped. 
#### Packet scheduling 
Packet scheduling is the way to determine what packet is transmitted to the link first, and there is many different ways of schedule the packets. 
##### First-come-first-served (FCFS)
<sup>Also known as First-in-first-out (FIFO)</sup>
This is the most simple way to deal with packet scheduling, and the most normal way we queue as humans. When we enter the queue we go to the back and wait for all the others to be done. This way the first one to arrive in the queue gets served first and the rest has to wait. 
##### Priority queue 
The priority queue works a lot like the queues at airports, where there is a premium queue for the people paying more. This is done with packets and any field in the header can determine what packets get priority and not. For example the ISP might decide that packets from a certain ip address has a higher priority and then they get priority. With priority queue all the low priority packets have to wait for the high priority packets to be sent. Within the separated queues the packets use the FCFS scheduling. 
##### Round robin (RR)
This type of scheduling works a lot like priority queuing, but there is a major difference. Instead of the lower priority having to wait for all the higher priority the service is alternated through all the queues. Traffic is still classified into different queues but this ensures that all packets eventually get service, even the low priority ones. 
##### Weighted fair queuing (WFQ)
In round robin every queue gets the same amount of service each time, but with weighted fair queuing this is determined by a weight $w_i$. Often the sum of $w_i$ will add up to 1 and we get this formula: 
$$
QueueService_i=\frac{w_i}{\sum_j{w_j}}
$$
If $\sum_j{w_j}=1$ then the link bandwidth per queue is:
$$
BandwidthPerQueue = {R}*{w_i}
$$




