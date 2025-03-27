# Sketch note: 2025-03-13 08:15

# KTN - 13.03.25

## Link layer, LANs

### Channel partitioning
- Splits the link to different partitions

### Random access
- Channel not divided and everyone can
- Allow collision and recover from this

### Taking turns
Slave-master:
- Nodes take turns, but nodes with more to send can take longer turns
- Master node invites the other nodes
- Used with dumb devices 
- Concerns:
	- Polling overhead
	- Latency
	- Single point of failure

Token passing:
- Control token passed one node to next sequentially
- Token message
- Concerns:
	- token overhead
	- latency
	- single point of failure (token)

### Cable access network

noe noe noe



## LANs
Addressing, ARP

MAC address:
- Usually follows the hardware
- 48-bit MAC address 
- Used locally to get frame from one interface to another physically connected interface

MAC address is like a social security number


# Trådløse nettverk

#mobilenetworks

SNR: signal-to-noise ratio
Det er hvor mye støy det er i forhold til signal. Det skal være m
Med høyere SNR så blir det bedre signal. og mindre BER 


# Security
#cybersecurity

## Confidentiality 

Handler om at bare mottaker skal skjønne meldingen. 
- sender vil kryptere
- mottaker vil dekryptere

## Authentication 

Være sikker på hvem mottaker er og om det er riktig mottaker (vg.no er faktisk vg)

## Message integrity

Sikre at en melding ikke har blitt endret på. 

## Access and avaliability

Tjenester må være tilgjengelige til brukere. DDOS kan være et eksempel på noen som angriper tilgjengeligheten. 


## Hva gjør bad guys

- eavesdrop
- actively insert messages 
- impersonation
- hijacking
- denial of service

# Cryptograhpy

meldingen er først plaintext, så vil den bli encrypted with Ka. så kan Kb dekryptere det. 

## Breaking an encryption scheme

two approaches: 
- brute force: try all keys
- statistical analysis 

Can be a bad algorithm where you only swap out the letters, and you can spot letters by how common they are in the alphabet. 

## Symmetric key cryptography 

Ks brukes både til kryptering og til dekryptering. Det er viktig å formidle nøkkelen og blir fort vanskelig når vi ikke kan gi den i person. 

#### Substitution cipher 
This is when you map each letter to another letter in the alphabet. 

You can also use n substitutions. 
When you also cycle the pattern of substitution you will get a harder to decipher pattern.

# DES: data encryption standard
- US encryption
- symmetric key
- cipher block chaining

It is not secure, and can be brute forced in less then a day.

3DES is better because it is harder to decrypt. 

# AES: advanced encryption standard

- symmetric key
- processes data in 128 bit blocks
- 128, 192, or 256 bit keys

Brute force decryption taking 1 sec on DES, takes 149 trillion years on AES


# Public key cryptography 
Sender and receiver does not share secret key. 

Public encryption key known to all.
Private decryption key known only to receiver.

Public and private keys is a revolution in cryptography because it is way easier. 


# Digital signature

Verifiable, nonforgeable: recipient can prove to someone that bob and no one else must have signed document

A signature can be that you send the encrypted version with the message, and then you can decrypt the message and match them. If there is a difference then the message has been intercepted. 

# Message digests 
#hashfunction #hash


computationally expensive to public-key-encrypt long messages.

Goal fixed-length easy-to-compute digital fingerprint
- apply hash function H to m, get fixed size message digest H(m)

Hash function properties:
- many-to-1
- produces fixed-size msg digest
- given message digest x, computationally infeasible to find m such that x = H(m)

## Internet checksum: poor crypto hash function

large message m -> H(m) -> Kb-(H(m)) encrypted message digest is sent with m

gets message and encrypted message digest

decrypts the message digest and hashes m

Alice gets two H(m) and compares the two

### Big hash functions
- MD5 
- SHA-1 


# Public key Certification Authorities

Entity will register entities public key with CA and provides proof of identity to CA.

- CA creates certificate binding identity E to E's public key
- certificate containing E's public key digitally signed by CA: CA says "this is E's public key"


# Virtual private networks

### IPsec service 

- data integrity
- origin authentication
- replay attack prevention
- confidentiality

Two variants:
- transport mode
- tunnel mode

In transport mode only the datagram is encrypted
In tunnel mode entire traffic is encrypted

Two protocols:
- Authentication header (AH)
- Encapsulation Security Protocol (ESP)
	- More widely used

### 802.11 authentication, encryption

Arriving mobile must:
- Associate with access point: establish communication over wireless link
- Authenticate to network

(1) discovery of security capabilities:
- AP advertises its presence, forms of authentication and encryption
- Device then requests the specific form of authentication and encryption desired

(2) mutual authentication and shared symmetric key derivation
- AS and mobile already have shared common secret (password)
- AS and mobile use shared secret, nonces
- 




