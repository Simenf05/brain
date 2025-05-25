2025-05-24 18:34

Status: #in-writing 
Tags: #communication #tcp #transportlayer #demultiplexing #multiplexing #rdt #it #http 

# Transport control protocol

### Overview of tcp
TCP is one of the most used protocols and is the backbone of [[Hypertext transfer protocol|http]], [[Simple mail transfer protocol|smtp]] and many more [[application layer]] protocols. The reason for this is that it provides a reliable interface to send form one-to-one over the unreliable network. The protocol does not provide message sending like [[User datagram protocol|udp]], but a full in-order byte tunnel for sending. It also provides full duplexing of data and allows sending in both directions. This protocol really is the best thing ever invented. 
The protocol uses cumulative ACKs like [[go-back-N]], and also pipe-lining and flow control to not overwhelm the receiver. TCP is connection oriented so it will require a handshake before any data can be sent.

### TCP segment structure

| 16 bit                             |          | 8 bit    | 16 bit               |
| ---------------------------------- | -------- | -------- | -------------------- |
| source port #                      |          |          | destination port #   |
| sequence number #<br>              |          |          |                      |
| acknowledgement number #<br>       |          |          |                      |
| header len                         | not used | CEUAPRSF | receive window<br>   |
| checksum                           |          |          | urg data pointer<br> |
| options<br>                        |          |          |                      |
| application data (variable length) |          |          |                      |

### TCP timeout values




## References