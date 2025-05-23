2025-05-22 09:58

Status: #finished
Tags: #communication #technology #transportlayer #applicationlayer #networklayer #linklayer #physicallayer 

# Layers in the networking
### The five layers of the networking stack

1. Application layer
	- [[Hypertext transfer protocol|HTTP]], [[Domain name system|DNS]], SMTP, IMAP
	- Is the protocols that power applications
2. Transport layer
	- [[tcp|TCP]], [[udp|UDP]]
	- Can implement [[Reliable data transfer|reliable data transfer]]
	- Data on the layer is called *segments*
3. Networking layer
	- [[Internet protocol|IP]], routing protocols
	- Data on this layer is called *datagrams*
	- Makes sure the *datagrams* is routed right, but not reliably
	- This is host to host while transport layer is process to process
4. Link layer
	- [[ARP]]
	- Sending between links on the network 
	- Data on this layer is called a *frame* 
5. Physical layer
	- The ethernet or wifi or other media

### Encapsulation in networking

The process of taking data from upper layer and adding header information to that data is called encapsulation. 
When data is sent over the network, the data will be encapsulated on the senders side and read and acted upon on the receivers side. Some of the layers will have to be read by nodes in the end to end connection.
## References
[Jim Kurose video](https://www.youtube.com/watch?v=IZ_PnVXtMeY&list=PL1ya5dD_M8uX-BLUF1FEvUNsYWQL5_l0O&index=5)