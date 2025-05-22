2025-05-20 13:05

Status: #in-writing 
Tags: #communication #technology #it #performace 

# Performance in networks

### 4 main ways of delay in packet switches

1. Processing delay
	- Caused by checking for bit errors
	- And for determining the output link
2. Queuing delay
	- Time to wait for other packets
3. Transmission delay
	- Packet length / transmission rate 
	- L / R
4. Propagation delay
	- The time it takes to send the packet from sender to receiver
	- Bepends on physical media
	- length / speed
#### [[traceroute|Traceroute]]
This can be measured by using [[traceroute]]. The program finds the [[round trip time]] to each of the routers in the connection. As the last step it measures the [[round trip time]] of the end to end connection.
### Packet loss
Every packet switch has a buffer with finite storage, and this means that the packets will have to be dropped if there is too much delay. This can cause more delays as packets will have to be retransmitted to be restored. 
### Throughput
Is the bits / time unit. This can be an average over a longer period of time or be in an instant at one specific time. 
End to end throughput will always be the lowest of the throughput's in the entire connection. This throughput can be described as the min function of all the links in the end to end connection. The link that limits the throughput is often called the bottleneck link.
## References
[Jim Kurose youtube video](https://www.youtube.com/watch?v=hm1y4LsphQQ&list=PL1ya5dD_M8uX-BLUF1FEvUNsYWQL5_l0O&index=4)