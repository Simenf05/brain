2025-08-26 10:23

Status:
Tags:

# Produksjon av integrerte kretser
Starter med silicon som deles opp til blank wafers. Så går mann igjennom mange steg som lager patterned wafers. Noe kommer ikke til å funke, så tar bort det. Etter det så pakker mann de sammen, så må det testes siden mann mister noen, så deaktiverer de og sender til bruker. 

### Hva er ytelse i datamaskin?
- Kjøretid
	- Tiden det tar fra du starter til det er ferdig 
	- Lavere tall er bedre
- Gjennomstrømning (throughput)
	- Mengden arbeid gjort per tidsenhet
	- Høyere tall er bedre
- Ytelse er invers kjøretid
	- Høyere er bedre

$Performance_x= 1/ExecutionTime$


### Clock

Datamaskiner er (ikke alltid) synkrone digitale systemer

Dette betyr at oppførselen til systemet kontrolleter av et klokkesignal

### The iron law

"...the only complete and reliable measure of computer prerformance is time."

$$
Kjøretid = klokkesykler per program * Sykeltiden 
$$
$$
Sykeltiden = 1 / klokkefrekvens
$$

$$
Intstruksjoner per prog * Klokkesykler * Sykeltid
$$
Vi setter ofte program som konstant og Sekunder / clock cycle konstant
Det gjør CPI proporsjonalt med kjøretid og IPC proporsjonalt med ytelse.

For å sammenligne tid så regner vi ut speedup tid
$SPEEDUP_TID = T_baseline/T_ny$

Energieffektivitet

Vi trenger benchmarks for å test ytelse på datamaskiner. Disse burder representere last som systemet skal gjøre. 

Amdahls lov er viktig. 
"Make the common case fast"


## Transistorer

Vi har to typer transistorer i dette kurset.

- PMOS
	- leder strøm når det er lav spenning
- NMOS 
	- leder strøm når den har høy spenning


