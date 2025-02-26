2025-02-23 16:19

Status: #in-writing
Tags: #rdt #it #communication #transportlayer #tcp #roundtriptime 

# Reliable data transfer

The reliable data transfer protocol can be divided up into many iterations of the same idea; ensure reliable end to end communication. Therefore this page will have sections that build upon each other, and at the end conclude by referencing the transport control protocol that is used today. 

The idea behind reliable data transfer is that the sending process and the receiving process should both have an interface that in some way ensures the completeness of the message. This is done by having a standard for what to send in the unreliable channel, and evaluating the results. 

Sender:
- The sender does not know the state of the receiver, so this has to be communicated.

---
## rdt1.0: transfer over a ==reliable channel==

We will first consider both the sender and receiver as finite state machines, and the channel used will be a perfectly reliable channel. This means that there can be no bit error or packet loss. 
In this example the transfer control is easy. For we only have to send the message in the channel has to receive it. This is almost never the case tho. 

---
## rdt2.0: channel with ==bit errors==

In this example the channel is not perfect, and it might flip bits in packets. This means that when a packet is sent, any part of that packet might not contain the right bits. In many scenarios broken packet cannot be used for anything and therefore we need to prevent them. 
### The real question; how to recover from errors?
rdt2.0 implements a layer of security by having a system of acknowledgments (ACKs) and negative acknowledgements (NAKs). 
### ACKs
An ACK is an acknowledgement that the packet was received and wasn't corrupted on the way. This is a packet sent by the receiver to the sender. When the sender receives the ACK it knows that the packet was successfully transferred. 
### NAKs
NAK is the packet that the receiver will send back if the packet was corrupted. When the sender receives this packet it will resend the last packet. 
### The flow
In this model the sender must wait for the receiving of the ACK or NAK. And when the receiver has sent the ACK or NAK, it too has to wait for the sender to receive it before the sender will send the next packet. This makes this model very slow and impractical for big amounts of packets. 
#### The fatal flaw
There is also one fatal flow of the model; what if the ACK is corrupted. In this case the sender would be left hanging, and the entire system would crumble down. 


## rdt2.1: handling bad ACKs/NAKs
To handle bad NAKs and ACKs, the sender should send sequence number with every packet. If the sender ever receives the bad NAK or ACK it will always resend the packet. Therefore the client also have to know what packet is current state, and discard any duplicates. This way we know that the information will be complete. 
In the case there is only needed two sequence numbers, because the protocol uses stop-and-wait so it will only be one packet at a time.


## rdt2.2: the NAKs-less protocol
Instead of sending NAKs the receiver will send two or three ACKs of the same packet for NAKs. This way the ACKs also have to use sequence numbers, but we can avoid having NAKs at all ([[tcp]] uses this).

---
## rdt3.0: channels with **error** and **loss**

**New channel assumption:** the channel can have loss of packets and ACKs
- Checksum, sequence numbers, ACKs and re-transmits will be of help but not enough

**The method**
The sender will have a timer that keeps track of how long its been since the packet was sent. If the timer runs out and the sender haven't received ACK for the packet then the sender will resend that packet. The receiver already handles duplicates, so this isn't a problem anymore. 

---
## The cringe of stop-and-wait
When using a model based on stop-and-wait we loose a lot of performance because of the wait for [[round trip time]]. The sender could be doing a lot more in the time before the first ACK is received. 

## Using pipe-lining to send multiple packets

The use of pipe-lining helps the sender spend more of the time doing productive stuff. The concept enables the sender to send many packets right after each other. Then it can wait for all the packets to be sent at the same time, instead of waiting for each packet alone. This makes the performance much better because you only need to wait one [[round trip time]] for the entire bulk of packets. 

But how do we handle the loss and knowing what to re-transmit? There is two solutions to this problem: 
- Go-Back-N
- Selective repeat

### Go-Back-N
The first option is to use a method called go-back-n. In this model the sender has a window of up to N transmitted but unACKed packet. 

### Selective repeat









## References