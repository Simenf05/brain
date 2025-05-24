2025-02-23 16:06

Status:
Tags: #it #communication #technology #transportlayer #udp #tcp #rdt #multiplexing #demultiplexing

# Multiplexing and demultiplexing

Multiplexing is the operation of taking all the messages sent from each of the different sockets on the host and uniting them to be given to the [[networking layer]]. Demultiplexing is the opposite operation where the the [[Transport layer|transport layer]] receives segments from the [[networking layer]] and has to read the headers and distribute the segments to the different sockets on the host. 

The protocols [[User datagram protocol|udp]] and [[Transport control protocol|tcp]] has different ways of multiplexing and demultiplexing. UDP will multiplex only on the destination ip and destination port. This way the receiver will not know the difference between multiple senders that send to the same port. This would not work with tcp because tcp is connection oriented, so tcp segments include both source and destinations ips and ports. This way the receiver will know exactly what connection it got a message from, and can reply to the correct port of the sender. 





## References