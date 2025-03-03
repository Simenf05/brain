# Sketch note: 2025-03-03 08:20

# KTN - 03.03.25

## IP addresser

NAT natwork address translation
Nat er når ruteren oversetter pakkene til å ha ip-en som brukes på internet
offisielle ip-er kan bare brukes en gang og kan nås på internet
de lokale ip-ene 


NAT: 
private nett: 10/8, 172.16/12, 192.168/16
Det er smart å separere isp og kobling utover fra ditt nettverk

### NAT table
Den vil lagre ip-en utover for seg selv og en fritt valgt port 
Dette vil den lagre med LAN infoet. Det vil si lokale ip og lokal port til processen som sendte koblingen. 

Når det kommer trafikk tilbake så kan den oversette tilbake. 

NAT er kontroversielt siden vi vil ikke at rutere skal tukle med ting på transport layer

Adresse problemet brude løses med ipv6


## IPv6

Det holder ikke med 32-bits ipv4 sine adresser så vi trengte flere.

De har også fixed lengde på header på 40 bytes.
ipv6 har 128-bits for adresser. 

IPv6 har tatt bort:
- no checksum
- no fragmentation
- no options

Tunneling er å pakke inn ipv6 pakker i ipv4 når det skal sendes til rutere som ikke støtter ipv6.

Det tar veldig lang tid å bytte til ipv6. Men det er en god endring. 