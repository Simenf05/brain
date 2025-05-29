---
aliases:
  - link layer
---

2025-05-27 15:52

Status: #in-writing 
Tags: #communication #linklayer #switch #link #mac #arp 

# Link layer
The link layers main responsibility is to transfer frames from one node to another physically adjacent node over a link. This link can be a wired cable or any wireless technology of any sort. The link layer frame encapsulates the [[Network layer|network layers]] datagram, and different physical links will have different types of frames. For example with ethernet almost no error correction is implemented because there is not that much loss, but with WiFi we need to have error correction. The link layer also has services that provide [[Transmission control protocol#Flow control|flow control]] like in the [[transport layer]], but on this layer its more about not overwhelming the next node instead of the destination host. With different link types some of them allow for full-duplex, meaning that traffic can flow both ways at the same time. Other links might only have half-duplex meaning traffic only can flow one way at the same time. 
## Error detection and recovery
To detect and recover from bit errors in the link layers multiple strategies are used. This is often done by adding error detection bits (EDC bits) at the end of the frame, with this the receiver can evaluate the bits received and detect when there is errors and sometimes even recover from the errors.
### Parity checking
The concept of parity checking is taking the payload and adding one bit to make the payload have an even amount of 1 bits. That means that if the bits you want to send already has a even number of bits then the last bit should be 0, if not then the bit should be 1. This way the receiver can detect when an odd number of bits has flipped, but has no way of exactly knowing where the flipped bits is. 
#### Grid based parity checking
Normal parity checking can be expanded to using a column and row based system. In this system you would have $i$ rows of bits and $j$ columns of bits. Then you could compute the parity of each row and column and add parity bits $i+1$ and $j+1$. Then when the receiver checks the parity bits it could detect where the single bit error is and restore it. With an approach like this we could build a smarter detection and correction technology at the cost of having to send more EDC bits.
## Checksum
A checksum can also be used just like how it is used by [[User datagram protocol|udp]], but because there exists stronger alternatives to the checksum its not much in use. For how to compute checksum see this [[User datagram protocol#How to calculate checksum]] and it is important to remember that there might still be error even though the checksum indicates no errors. 
## Cyclic redundancy check (CRC)
A more robust approach to checking the integrity of frames can be done using the cyclic redundancy check. With this test you can be sure of the result up to $r+1$ errors when adding $r$ EDC bits to the frame. CRC works by calculating a $R$ of length $r$ based on a generator $G$. The generator has to be known by both parts of the communication and therefore it is part of the CRC standards. In the CRC32 standard provided by [[Institute of Electrical and Electronics Engineers|IEEE]] does the generator have a length of 32 bits, and with this you can detect all errors less then 32. This is why CRC is used widely in WiFi and ethernet. 
#### How it works
Why you have a payload $D$ with $d$ bits of payload and EDC bits $R$ with length of $r$ you will end up with a $DR$ of length $d+r$. When you know $D$ and $R$ we get:
$$
DR = D*2^r\oplus{R}
$$
To compute R we use this formula:
$$
R = remainder[\frac{D*2^r}{G}]
$$
When calculating this you would get the $R$ of length $r$.
## Medium access control (MAC)
The medium access problem is designing a protocol for transmitting over a shared link, while avoiding collision. Difficulty of the medium access problem stems from having to maintain state shared state in the protocol without transmitting over the link. There are three main medium access protocols and they solve the problem in different ways. 
### Channel partitioning 
With channel partitioning the main principle is to divide up the shared medium and giving all users the same amount of bandwidth. This can either be done with time slots or with separate frequencies for the users. 
#### Time division multiple access (TDMA)
This protocol is really simple because it divides the channel into different slots and allocates the slots to the different nodes. That way every node gets $R/M$ for $R$ transmission rate and $M$ nodes. The problem with this approach is that if nodes dont have anything to send the channel will go idle. Therefore if there is many nodes and some of them are idle it will greatly impact the utilization of the channel. 
#### Frequency division multiple access (FDMA)
With frequency division multiple access instead of splitting up the usage in time on the channel, the channel is rather divided based on the frequency used. This way every node can have full access to the channel all the time but at reduced capacity, sadly this approach only works for certain mediums, [read more here](https://www.geeksforgeeks.org/frequency-division-multiple-access-fdma-techniques/).
### Random access
In the random access protocols we just hope that the channel inst busy. That way we still have a risk of getting collision on the channel, which will result in none of the frames being transmitted correctly. Random access protocols define how to detect when there is collision and how to recover from it, this is done by re-transmitting at a random later interval. 
#### ALOHA 
The ALOHA protocol was one of the first protocols to put the random in random access, and this is because it chooses a random time to try re-transmission. In this protocol all the frames are the same size and time is divided into equal time slots of the time it takes to transmit one frame. Then the nodes will try to transmit at the start of time slot, and if two or more nodes transmit in a single time slot we get collision. But this is part of the protocol, because then all the nodes that got collision will have a randomized backoff time before trying re-transmission. The cons of the protocol is that there can end up being a lot of waste with both the time slots that have collision and the slots that are idle because of the random backoff. The protocol also has to be synchronized, meaning that it can be harder to maintain. 
#### Carrier sense multiple access (CSMA)
In the most simple version the carrier sense multiple access protocol the principle is to check if another node is transmitting on the channel before transmitting. This way the sending node can defer the transmission and avoid collision. But there might still end up being collision if the first sender starts sending and then the second sending also starts sending before the first nodes frame reaches the second node. That is why CSMA/CD exists. 
##### Collision detection (CSMA/CD)
This implements the same listening as normal CSMA but also listens for collision after starting transmission. That way both sending nodes can backoff early and start re-transmission faster. Collision detection is easy with wired connection but hard on the wireless. The backoff time is determined by binary exponential backoff which after $m$ collisions, choose $K$ at random from $\set{0, 1, 2, ..., 2^m-1}$ and then it waits $K*512$ bit times. This means that the more collisions there is the longer the backoff time is. 
### Taking turns
Taking turns is based on having the best of both worlds in the sense that the channel is divided to avoid collision, but nodes not holding the channel when the dont have anything to send. There is two approaches to this method. 
#### Token passing
With token passing the nodes are usually displayed in a circular manner, where there is one (or more) token being passed around in the circle and when you have the token you are allowed to use the shared channel. The problem with this is that there is a single point of failure, and if the node with the token leaves then the node leave with the token. 
#### Polling 
In polling instead of having one token we instead have a node that is responsible for giving each node the channel. The problem with this method is again that there is one point of failure. 
## Addressing
For addressing the link layer uses a address called the MAC address. These are 48 bit long and is connected to the network interface controller (NIC). The MAC address of an NIC is static and therefore never changes and this means that the MAC address has to be able to travel from network to network without changing. So to send something to someone one the link layer you would need the MAC address, but how do we find the MAC address when we only have the [[Internet protocol|IP]] address. Read about [[address resolution protocol]] for how to get MAC addresses from only having the IP address. 


