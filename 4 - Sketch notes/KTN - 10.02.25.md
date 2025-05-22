# Sketch note: 2025-02-10 08:10

#it #communication #technology #transportlayer #tcp
## [[Transport layer]]


- utilization - fraction of time sender busy sending

1 Gbps link, 15 ms prop. delay, 8000 bit packet
- time to transmit packet into channel:
- Dtrans = L/R = 8000 bits / 

### rdt3.0: stop-and-wait
rdt3.0 protocol performance stinks!

### rdt3.0 pipe lined protocol operation

Pipelinning: sender allows multiple "in-flight" yet to be acknowledged

- Range of sequence numbers must be increased 
- Buffering at sender and/or receiver

#### Pipelinning: increases utilization

---
### Go-Back-N: sender

sender "window" of up to N, consecutive transmitted but unACKed pkts
- k-bit seq # in pkt header

Cumulative ACK: ACK(n): ACKs all packets up to, including seq # n
- on receiving ACK(n): move window forward to begin at n+1
timer for oldest in-flight packet
timeout(n): retransmit packet n packet n and all higher seq 

når den ikke får ACK på en pakke så vil den Go-Back-N og starte fra det som ikke ble ack-a
det bestemmes fra timeout


### Go-Back-N: reciver

ACK-only: always send ACk for correctly received packet so far, with highest in-order seq #

On receipt of out-of-order packet
- can discard or buffer 
- re-ACK pkt with highest in-order seq #
- It will send duplicate ACK of the last one it received when getting out of order

---
## Selective repeat 

recevier individually acknowledges all correctly received packets

sender times-out retansmits individually for unACKed packets

will [[ack]] out-of-order and 

### Sender
- data from above
	- if next available seq # in window, send packet
- timeout(n):
	- resend packet n, restart timer
- ACK(n) in

### Receiver 
- send ACK(n)
- will keep out-of-order in the buffer and [[ack]] it
- timeout will end on the missing packets and sender will resend

Does not need to go back and send a lot more. But must have buffer on client side.

### Dilemma

seq \#s: 0, 1, 2, 3 (base 4 counting)
window size=3

if the [[ack]] is not received then the receiver will move window but the sender will resend the same packet.

The order will be messed up.

---
## Go-back-n vs Selective repeat

Go-back-N max window = 2**n -1
Selective Repeat max window 2 ** (n-1)

---
## TCP: overview
#tcp 

- point-to-point
	- one sender, one receiver
- reliable in-order byte-stream
	- no "message boundaries"
- full duplex data
	- bi-directional data flow in same connection
- cumulative acks
- pipelinning 
	- congestion control and flow control
- connection-oriented
	- handshaking
- Flow control
---
### TCP sequence numbers, ACKs


User type "C"
Host ACKs receipt of "C", echoes back "C"
Host ACKs receipt of echoed "C"

---
### TCP round trip time, timeout
#roundtriptime #timeout

timout needs to be more than [[round trip time]] 
if timeout is to low then you will get premature timeout
if it is to high you will get latency

The best is to measure the time from segment transmission until ack receipt

EWMA (exponential weighted moving average) is used to calculate the [[round trip time]].
past values will determine the value
typical value: a=0.125

You still need safety margin so will calculate more than [[round trip time]].


## TCP sender

create segment with seq #

seq # is byte-stream number of first data byte in segment
start timer if not already running

#### event timeout 
- retransmit segment that caused timeout
- restart timer

#### event Ack received 
- move sendbase
- if not


### TCP receiver Ack generation

---
### TCP fast retransmit

Receipt of three duplicate ACKs indicates 3 segments received after a missing segment - lost segment is likely. So retransmit
##### Why 3 acks????
There is a lot of science to find the fastest way to retransmit.

Will often be faster then waiting for timeout.

---
### TCP flow control

It is about not overpowering the receiver. 

