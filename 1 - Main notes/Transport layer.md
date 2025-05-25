2025-02-14 14:56

Status:
Tags: #communication #tcp #it #rdt #roundtriptime #udp #applicationlayer #networklayer 

# Transport layer

The task of the transport layer is to provide a logical connection between different [[process|processes]]. The connection is used between different hosts meaning usually different machines or servers on the same network or over the internet. 

### House example
An analogy to this layer could be that if there was two houses with 12 children, then the host would be the house, the children would be the [[process|processes]] and letters sent between the houses would be transported by the transport layer. The transport layer has to know if a letter went missing on the way and resend lost letters.

### Transport layer protocols: TCP and UDP

The main two transport protocols is [[Transmission control protocol|TCP]] and [[User datagram protocol|UDP]]. They both divide the message to send up into ==segment==.
The difference between them is that TCP is connection-oriented and UDP is not. UDP does not require the processes to handshake and has no guarantee that it is reliable. TCP fixes this by implementing connection-oriented communication. With this it can guarantee that all segments will be sent and received. 

### [[Multiplexing and demultiplexing]]
The transport layer will break up the [[application layer|application layers]] message into parts called segments. This action is called [[multiplexing and demultiplexing|multiplexing]] and is one of the responsibilities of the transport layer. When splitting up the message it is easier to verify that the message is received properly, and the network requires packets to be smaller anyways. These segments is then passed to the [[networking layer]].

## [[Reliable data transfer]]

Reliable data transfer is the protocol that ensures that all data is delivered from end to end. The technology that is used today is the [[transmission control protocol]], but we will not start on that protocol. On the page [[Reliable data transfer]] we will develop the protocol and at last we will arrive on the [[Transmission control protocol|tcp]].



## References