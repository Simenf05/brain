# Sketch note: 2025-03-10 08:16

# KTN - 10.03.25

# Link layer and LANs

Prinsipper av link layer:
- Det er også error detection men her så er det ikke ende til ende
- Håndtere medie-tilgang og hvordan flere tilganger er koblet. 
- Link layer addressing 
	- Vi har noen addresser som bare har noe å si på link layer
- MAC adresser (multiple access protocols) 
- LANs
	- addressing, ARP
	- Ethernet 
	- switches
- a day in the life of a web request

## Link layer

Det er mellom to noder, og kobler de sammen. Alle koblinger er uavhengige av hverandre. 

The main responsibility of the link layer is to transfer a datagram from one node to the next physical link.
Layer-2 packet: frame, encapsulates datagram.

The link layer has to abstract away all the physical devices and make it easy to send on many devices. (Kind of like the kernel)

Link layer may or may not contain reliable data transfer.
## Link layer services 

- framing, link access:
	- encapsulate datagram into frame, adding header, trailer
	- channel access if shared medium
	- "MAC" address in frame headers identify source destination (different from ip address)
- reliable delivery between adjacent nodes
	- Nice to make more reliable data transfer lower in the stack
- Flow control
	- pacing between adjecent sending and receving nodes
-  Error detection 
	- errors caused by signal attenuation noise
	- receiver dtects error, signals retransmission, or drops frame
- error correction
	- receiver identifies and corrects bit errors without retransmission
- half-duplex and full-duplex
	- with half duplex nodes at both end of link can transmit, but not at the same time

### Where is the link layer implemented?

Link laget ligger på nettverkskortet til den fysiske maskinen. 

#### Physical mediums  

Twisted pair
 - two copper wires twisted
 - reduces noise

Coaxial cable
- Two concentric copper conductors

Fiber cable 
- Glass fiber carrying light pulses, each pulse is a bit.
- high-speed operation
- low error rate

Radio link
- terrestrial microwave
- wireless LAN
- wide-area 
- satelite 

## Cyclic Redundancy Check (CRC)

CRC of r bits can detect 
- All burst errors < r+1 bits
- All odd numbers of bit errors
- burst error > r+1 detected with probability 1**-0.5r

View data bits ad binary number
Choose a generator G = r+1 bits
- First and last bit = 1
- Generator bits are one more than the CRC bits
Find r CRC-bites, R, such that
- <D,R> exactly divisible by G (modulo 2)

R is the remainder witch must be added to D in order to get <D,R>

#### What is a generator
Can be polynomial or binary 

x⁴+x³+x+1
\=
11011

