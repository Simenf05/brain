2025-05-27 15:52

Status: #in-writing 
Tags: #communication #linklayer #switch #link #mac #arp 

# Link layer
The link layers main responsibility is to transfer frames from one node to another physically adjacent node over a link. This link can be a wired cable or any wireless technology of any sort. The link layer frame encapsulates the [[Networking layer|network layers]] datagram, and different physical links will have different types of frames. For example with ethernet almost no error correction is implemented because there is not that much loss, but with WiFi we need to have error correction. The link layer also has services that provide [[Transmission control protocol#Flow control|flow control]] like in the [[transport layer]], but on this layer its more about not overwhelming the next node instead of the destination host. With different link types some of them allow for full-duplex, meaning that traffic can flow both ways at the same time. Other links might only have half-duplex meaning traffic only can flow one way at the same time. 
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

## Multiple access control (MAC)


## Addressing






