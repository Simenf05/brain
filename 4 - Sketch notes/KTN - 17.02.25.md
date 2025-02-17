# Sketch note: 2025-02-17 08:18

# KTN - 17.02.25

#transportlayer #communication #it #technology 

# [[tcp|TCP]]

## Flow control
Handler om å kontrollere hvor raskt mann sender informasjon inn i nettverket. Det kan ha hensyn for en blid mottager og for nettverket. Det er alltid begrensa hvor raskt nettet og mottakeren kan ta det. 

Vi har buffer som lagrer info hvis det er noe som blir tapt. Den mellomlagrer data. Hvis data kommer for fort så må vi ha buffer som håndterer det. 
Eks:
- Gammel pc og ny pc

Flow control handler om å ikke gi for mye til bufferen.

#### Receive window

Jeg sender mitt vindu til deg slik at det er mulig å vite hvor mye som kan sendes på en gang. Hvis for mye sendes så blir det buffer overflow og da går det mye tapt.

#### Buffer
Når det er snakk om buffer så tenker mann på hvor mange bytes den kan holde, IKKE hvor mange pakker siden de kan variere.

#### Handshake gjennom connection management

Handler om etablering av forbindelse og utveksling av startparametere. 

#### Mye som kan gå galt med 2-way connection
- Vi kan få problemer med half-open connection hvis server og client ikke er i sync. Det kan skje ved client prøver å koble til før serveren har rukket å sende at det har blitt kobla.

#### TCP har 3-way handshake

Client
 - tcp-syn
	 - SYNbit=1
	 - seq=x
Server
 - SynACK
	 - Synbit=1
	 - Seq=y
	 - ACKbit=1
	 - ACKnum=x+1
Client
 - SynAck
	 - Ackbit=1
	 - ACKnum=y+1



##### Close bit 
FIN bit = 1 betyr at tcp koblingen blir lukket. Både server og client kan gjøre fin.


### Congestion control
==Ikke det samme som flow control== 
Handler om kontroll av alle sendere over nettet. Ikke bare koblingen mellom en og en men heller hele systemet. 

VI kan vite at det sendes for mye hvis pakker går tapt. TCP bruker det som kan observeres for å vite om det er for mye trafikk. 

### Network-assisted congestion control
TCP ECN

### TCP phases

- Connection phase
- Transfer phase
	- Slow start
	- Congestion Avoidance

#### Slow start


#### Congestion avoidance



