---
aliases:
  - http
---

2025-05-23 11:51

Status: #in-writing 
Tags: #http #communication #applicationlayer #it #technology #tcp #www #protocol 

# Hypertext transfer protocol

### Basis for http
- Http transfers what is called objects (html files, jpeg, etc).
- The http protocol is stateless
- Uses port 80

### Two types of HTTP 1
#### HTTP 1.0
HTTP 1.0 is non-persistent which means that it only can transfer one object at a time. In practice this means that for every object that needs to be sent the client and server will have to handshake and establish a connection. This makes the protocol slow and bad for bigger websites. 

#### HTTP 1.1
HTTP 1.1 does mostly the same as 1.0, but allows the connection to stay open for sending of multiple objects. This way when the client first requests the index.html 

#### HTTP 2.0
#### HTTP 3.0 / QUIC
This version of http uses [[User datagram protocol|udp]] to transfer the objects instead of the standard tcp. With this approach more is done at the [[application layer]] to make sure we still have [[reliable data transfer]]. The QUIC protocol makes a handshake in just one [[round trip time|rtt]] and this is way faster then tcp's 2 [[round trip time|rtt]]s. QUIC also introduces parallelism to the protocol, so that there is no head of the line blocking. This means that if one of the objects is lost in [[Reliable data transfer|rdt]] then the others can send while there is recovery. This makes it much faster for certain tasks.


## References