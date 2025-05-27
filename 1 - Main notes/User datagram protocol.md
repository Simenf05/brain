---
aliases:
  - udp
---

2025-02-23 15:45

Status: #in-writing 
Tags: #it #communication #transportlayer #roundtriptime #technology #udp #protocol 

# User Datagram Protocol
The user datagram protocol is a connectionless protocol. This means that there is no need to establish a connection or have handshake between the sender and receiver. UDP is also a best effort protocol, and this means that it will do its best but fail sometimes. There is no guarantee that the message will make it across in order or at all. This is also why the protocol is so simple. It almost only contains destination port and ip. 

### Why do we need UDP
The UDP can be useful because it does not need a connection, and therefore it is faster to send data. [[Transmission control protocol|TCP]] would first have to wait a [[round trip time]] to establish the connection but in UDP there is no need for it. The headers are also small in comparison to other headers. 

### The UDP header

| 16 bits          | 16 bits  |
| ---------------- | -------- |
| # ip             | # port   |
| length           | checksum |
| Application data |          |

The UDP header only has four elements, and it is ip and port used for [[multiplexing and demultiplexing]] and routing on the network. And also the length that since the segment can have a variable length, and the checksum used for checking if the data has been corrupted on the transfer. 

#### How to calculate checksum
To calculate the checksum you would need to first treat the segment as 16 bit integers. This includes the header values and the data from the [[application layer]]. This way we get a long list of 16 bit integers like these two:

```
  1 0 0 1 1 0 0 1 0 0 1 1 1 0 0 0
  1 1 0 1 1 0 0 1 1 1 1 0 0 1 0 1 // take sum
  
1 0 1 1 1 0 0 1 1 0 0 0 1 1 1 0 1 // the 1 at the start carries over to the back
  0 1 1 1 0 0 1 1 0 0 0 1 1 1 1 0 // and gives

  1 0 0 0 1 1 0 0 1 1 1 0 0 0 0 1 // invert all the values
```

This is now the final checksum that we add to the header of the UDP segment.
It is important to state that even though the checksum matches at the receivers end, the data might still be corrupted. There is edge cases where two flipped bits still let the checksum turn out the same, and this is part of the reason that UDP is unreliable. 
## References