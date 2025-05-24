2025-05-23 10:07

Status: #in-writing
Tags: #communication #it #technology #applicationlayer #transportlayer #tcp #udp

# sockets
The socketing interface connects [[Transmission control protocol|tcp]] and other technologies from the [[transport layer]] with an standardized way of connecting. This makes it easier to make an application on the [[application layer]] without having to directly connect to tcp and struggle with that. 


### Addressing the socket
The socket has two main pieces of information that identifies the socket. 
- Ip address of the host
- Port number of the process on the host

Some ports are reserved for types of communication, like 22 for ssh and 25 for mail and 80 for http.

### There exists tcp and udp sockets


## References