2025-02-23 15:45

Status: #in-writing 
Tags: #it #communication #transportlayer #roundtriptime #technology #udp 

# User Datagram Protocol
The user datagram protocol is a connectionless protocol. This means that there is no need to establish a connection or have handshake between the sender and receiver. UDP is also a best effort protocol, and this means that it will do its best but fail sometimes. There is no guarantee that the message will make it across in order or at all. This is also why the protocol is so simple. It almost only contains destination port and ip. 

### Why do we need UDP
The UDP can be useful because it does not need a connection, and therefore it is faster to send data. TCP would first have to wait a [[round trip time]] to establish the connection but in UDP there is no need for it. The headers are also small in comparison to other headers. 


## References