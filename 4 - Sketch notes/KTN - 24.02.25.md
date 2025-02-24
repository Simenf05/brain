# Sketch note: 2025-02-24 08:17

# KTN - 24.02.25

### buffer **managment** 

- drop:
	- When the buffer is full the buffer will have to drop.
		- The most basic drop is tail drop, meaning dropping the last packet arriving
		- Can also drop the least important packet in priority drop
	- Marking
		- Marking packet to signal congestion (ECN, RED)
			- The marking can be done with port numbers or ip

### Packet Scheduling: FCFS

packet scheduling: Determine what packet to send next on the link

- first come first serve
- priority
	- will always prioritize the one that has priority
	- can starve other connections
- round robin
	- round robin will divide op each of the traffics and let each share the link
- weighted fair queuing
	- If you give them weight it might be better. 
		- One packet from w1, two packets from w2 and 3 packet from w3
		- Each will get the amount of bandwidth they need on the link

### Sidebar: Network Neutrality



## IP: the internet protocol

Network Layer: Internet

IP datagram format


Subnets

The first part of the ip is the subnet that the network is part of. The last number of the ip is the identity of the host. 






