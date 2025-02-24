2025-02-23 16:19

Status:
Tags: #rdt #it #communication #transportlayer #tcp 

# Reliable data transfer

The reliable data transfer protocol can be divided up into many iterations of the same idea; ensure reliable end to end communication. Therefore this page will have sections that build upon each other, and at the end conclude by referencing the transport control protocol that is used today. 

The idea behind reliable data transfer is that the sending process and the receiving process should both have an interface that in some way ensures the completeness of the message. This is done by having a standard for what to send in the unreliable channel, and evaluating the results. 

Sender:
- The sender does not know the state of the receiver, so this has to be communicated.
## rdt1.0: transfer over a ==reliable channel==

We will first consider both the sender and receiver as finite state machines, and the channel used will be a perfectly reliable channel. This means that there can be no bit error or packet loss. 
In this example the transfer control is easy. For we only have to send the message in the channel has to receive it. This is almost never the case tho. 

## rdt2.0: channel with ==bit errors==

In this example the channel is not perfect, and it might flip bits in packets. This means that when a packet is sent, any part of that packet might not contain the right bits. In many scenarios broken packet cannot be used for anything and therefore we need to prevent them. 







## References