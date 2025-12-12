2025-11-26 17:17

Tags: #dsa #algorithms #bellman-ford #dijkstra #sorting
# Algdat sammendrag
## Forelesning 1
Asymptotisk notasjon

- Theta 
	- Nøyaktig kjøretid
	- Se gjennom liste med tall
- Store omega
	- Nedre grense
	- Inklusiv
- Lille omega
	- Nedre grense
	- Eksklusiv
- Big O
	- Øvre grense 
	- Inklusiv
- Lille o
	- Øvre grense
	- Eksklusiv

### Insertion sort
-  $O(n^2)$

## Forelesning 2
En reduksjon er å ta et problem å omformulere det til noe annet.
Et eksempel er å åpne en kiste kan være vanskelig, åpne låsen kan være enklere.

Redusere fra A til B
-  Løser du B, så er det minst like vanskelig som A
- Hvis A er uløselig, så vil B også være det

#### Problemdefinisjon
R = en binær relasjon
Søkeproblem Verifikasjon
Beslkutning
Optimalisering

Reduksjonstyper
- Karp
- Turing
- Levin
- Cook

#### Dekomponering
For vært steg så bryter vi av en bit

Redusibilitet, løkkeinvariant og induksjon

### Lineære program
lineær ulikheter
lineær objektiv funksjon

Lineære program med heltall er np-hardt

## Forelesning 3
#### Divide and conquer
Dele opp problem i mindre instanser av det samme problemet
Bygger de sammen igjen så vi får en løsning på det store problemet

### Bisect and Bisect'
Binær søk, deler opp og søker i hver del
Den antar at listen er sortert
$O(lg(n))$

### Merge sort
Deler opp listen i to
merge-sorter begge delene
Bruker merge for å samle to  sorterte lister
$T(n) = 2T(n/2) + n$
$O(nlg(n))$

### Quicksort
Velger et pivot element.
Bruker partition for å dele listen i større enn pivot og mindre enn
Så kjører den quicksort rekursivt
Average
$O(nlgn)$
Worst case 
$O(n²)$

### Random Quicksort
Samme som quicksort men velger pivot random i stedet for i midten. 
Den har bedre amortisert kjøretid
$O(nlgn)$

## Forelesning 4
Sammenligningsbasert sortering kan ikke ha worstcase bedre enn $\Omega(nlg(n))$

### Randomize select
Skal finne k-te minste elementet i en liste
Velg random pivot
sorter lav venstre høy høyre
Hvis elementet er pivot er vi happy
ellers så søker vi riktig halvdel

$\Theta(n^2)$

### Select
Det er en veldig komplisert algoritme
Vi trenger å kjenne til den men ikke forstå alt
Bruker select for å velge pivot
$\Theta(n)$

### Counting sort
Tellesortering teller hvor mange ganger en verdi oppstår i en liste
vi bruker det til å plassere tallene i listen
Den kjører i linær tid. Hvis $k\leq{n}$ så kjører den i linær tid tror jeg les boka
$\Theta(n + k)$

### Radix sort
Vi sorterer etter siffer i tallene
Vi putter i bøtte siffer for siffer 
Starter med å sortere bakfra, også går vi fremover med siffer
Når vi bruker counting sort så har vi kjøretid:
$\Theta(d*(n+k))$

### Stabil rutine
Bytter ikke verdier som er like
Ivaretar relativ rekkefølge for like verdier

### Bucket sort
Jobber med bøtter
Legger gjenstandene som sorteres i bøtter også sorterer bøttene
kan ofte bruke insertion sort
Slår sammen alle bøttene til slutt

Vi antar at bøttene har $O(1)$ lengde
Worst case $O(n^2)$
Kjøretid $O(n)$

## Forelesning 5
### Tre
Er implisitt at vi snakker om rotfast tre
Har noder som peker ned på noder under.
Rot er på toppen av treet
Foreldre er over
Barn er under 
Løvnoder er noder uten barn

Ordnet tre
- Barna har rekkefølge
- Posisjonstre
	- Barn har en fast definert posisjon i treet
- Binærtre
	- Har kun to barn
		

### Binærtre
Binært søketre 
Venstre er mindre eller lik rot
Høyere er større eller lik
Gjelder rekursivt for alle nodene

##### Inorder-Tree-Walk
Vi starter på venstre bunnen og jobber oss bortover
##### Tree-Search
Søker rekursivt i et tre
har kjøretid $O(h)$
##### tree minimum
##### tree seccessor
##### tree insert
##### tree delete

#### Binær søketre høyde

Forventet høyde er $lg_2(n)$

### Hauger/Heaps
Max-heap betyr største på toppen
Min-heap betyr minste er på toppen

Er nice for å hente største eller minte i konstant tid

#### Heap algos

#### Max-heapify
tar verdien som bryter heap egenskapen
verdien flyter nedover

med flere algoritmer

### Heapsort
Bygger max heap
går fra bunn til toppen og legger det største elementet i slutten av listen
heapifyer på nytt

## Forelesning 6
### Dynamisk programming

#### Optimal delstruktur 
En optimal løsning består av optimale delløsninger
Vi kan dele opp i mindre biter
Kan løse de mindre bitene og kombinere til løsning for stor problem

#### Overlappende delproblemer
Delproblemer gjengår

#### Delinstansgraf 
Vite hva det er
Kan være hasse-diagram
#### Hva er DP
Overlappende delproblemer gjør det nyttig
Optimal delstruktur gjør det korrekt

#### Bottom-up
er en iterativ metode som deler det opp i mindre biter
vi løser først de minste bitene ofte med en for loop

#### Top-down 
Rekursiv metode
memoization betyr at vi sjekker om vi har løst et problem før
hvis vi ikke har det så løser vi det også lagrer det
ellers så bruker vi svaret vi har lagra før

### Stavkapping
Skal dele opp en stav i ulike lengder der alle lengdene har en pris du kan selge for
Om å gjøre å få høyest verdi

#### Bottom up for stavkapping
Vi starter med de minste bitene også 

### Longest Common Substring
Finner lengste substrengen som matcher for to strenger

### Knapsack problemet
Prøver å få mest mulig verdi i sekken
Binary knapsack er NP-hardt 
med desimaler så kan det løses

## Forelesning 7
### Grådighet
Baserer seg på grådighets-egenskapen
- Hva er det beste steget jeg kan ta her
- Trenger det kun for det første valget
Trenger også Optimal delstruktur

Grådighet og dp er to forskjellige metoder

### Aktivitets-utvelgelse
Kan gjøres både rekursivt og iterativt

### Kontinuerlig Ryggsekk

Fractional knapsack problem

Vi trenger ikke å jobbe med hele gjenstander
Det vil si at vi kan dele opp gjenstandene våre i mindre deler for å fylle sekken

Vi kan løse det effektivt

Vi heller det som har mest verdi helt til vi har brukt det opp
Når det er tomt så går vi videre  til de mindre verdifulle

### Huffman koder
Mål: redusere størrelse på tekst 

Bygger et tre ved hjelp av huffman tree
Huffman kode = optimal prefix kode

Slå opp huffmankoder i treet

Det er få bits for det vi ser ofte, og bruker flere tegn for det som er sjeldent

## Forelesning 8
### Grafer og traversering

#### Nabomatriser
Matrise som viser om $u$ er koblet til $v$
nabomatriser er raskt å slå opp i
Det er også treigere å traversere
det bruker mer minne
#### Nabolister
Liste med lister for naboene for hver node
det er kjapt å traversere og bruker mindre minne
Funker best for få kanter
treig å slå opp i

### DFS

Er en måte å traversere en graf på
DFS-visit starter fra en node også jobber seg helt ned til bunnen av treet, etter det så jobber den videre oppover
DFS gjør dfs-visit for alle nodene i grafen

Den farger også noder ettersom om de er sett, oppdaget men ikke ferdig, og helt ferdig
Bruker også time for å lagre når den fant og når den ble ferdig med en node

#### Klassifisering av noder
Hvit node = Tre-kant
Grå node = bakover-kant
Svart node = Forover-kant

En dfs-skog består av forjengerkanter
Alle de hvite nodene vi besøker i dfs er kanter i dfs-skogen

### Parantesteoremet
Når vi gjør dfs så åpner vi parantes når vi først besøker den node, når vi er ferdig så lukker vi parantesen


Start og slutttid for noden vil være mindre og større enn alle nodene v som u har en vei til
Gjelder for dfs tre

### Hvit-sti-teoremet 
Med en node v som kun kan nås fra v

Fra det tidspunktet v er nådd hvis det bare er mulig å nå u med hvite noder fra v så vil v bli en etterkommer fra u i dfs-treet

### BFS
Bruker en FIFO kø for å besøke alle noder på samme dybde

Den er definert fra en node og de som ikke kan nås vil ikke bli nådd.
Hvis det ikke er vekter i grafen eller at de er like så vil den finne korteste vei.
DFS: $\Theta(V+E)$
BFS: $\Theta(V+E)$

### Topo sortering

Krever directed acyclic graph (DAG)
Gir noder rekkefølge og sorterer etter rekkefølgen de er ferdige


### Strongly connected components

Alle noder når alle noder og vi har rettede stier

Målet er å finne de sterk-sammenhengende komponentene i en graf

Vi kjører dfs
Bytter retning på alle kanter i G
kjører dfs på nytt

## Forelesning 9
### Minimale spenntrær

#### Disjoint set
Make-set lager set
Union
Link
Find-set
Same-component

Roten av en mengde repper den mengden

##### Mer om grafer
Graf er noder og kanter
Snitt er noe som deler en graf i to
Delgraf er noen eller alle noder og kanter
Spenngraf nodesett som før
Spennskog asyklisk spenngraf
Spenntre sammenhengende spennskog

Minimalt (kostnad) spenntre har minst mulig vekt på kantene

### Generic-MST

Grådig måte å finne MST  på
Så lenge vi ikke har spenntre så finner vi kant som er trygg, legger til kanten

Trygg kant er en kant som ikke ødelegger for at mengden kanter kan bli et MST

Trykk kant bevarer invarianten
Lett kant er når vi deler grafen i to også tar vi den kanten med lavest vekt

For MST så kan vi lage snitt også velge den trygge/lette kanten

#### Kruskal
Legger til en lett kant som ikke lager en sykel
Bruker disjont-set for å holde styr på hva som er connected component
$O(E*lgV)$
#### Prim
Her så vokser treet fra en node der vi alltid finenr den nye kanten som har lavet vekt fra treet vårt nå
Bruker min-priority queue som dijkrtra
Kanten kan ikke skape en sykel
sjekker for sykel ved å sjekke om v i kanten (u, v) , om v er i køen
$O(E*lgV)$

## Forelesning 10
### Korteste vei En til alle
- En til alle
- alle til en
- en til en
	- Er likt som en til alle

Enkel sti => ingen sykel
Kortest sti => enkel sti
Negativ sykel => ingen korteste vei
Finnes en korteste enkle sti (men er np-hardt)

####  Shortest path tree
#####  Relaxing
Relaxer trekantulikheten
$v.d = u.d + w(u, v)$
Vi oppdaterer hva vi tror er den korteste veien til en node ($v$)

### DAG-shortest path
Finner korteste vei på DAG

Bruker topo sort på dag-en
Gå igjennom alle noder u også relaxer v der v er har $(u, v)\in{E}$
$\Theta(V+E)$

### Bellman-ford
Finner korteste vei, men kan også brukes for å finne ut om vi har en negativ sykel
bellman ford er definert for både positive og negative kanter

Finner den korteste veien ved å relaxe alle kantene V ganger
$O(VE)$

### Dijkstra
Finner korteste vei med vekt
Den er definert for kun positive vekter

Bruker en min-pri kø
Vi gjør antagelse om at noder med lavest verdi er ferdige
Funker ved å velge noden som har lavest $u.d$ og relaxer alle nodene den har kant til
bruker også trekantulikheten
$O(V*lgV+E*lgV)$

## Forelesning 11
### Alle til alle
#### Trekantulikheten
$\delta(i, j) \leq \delta(i, k) + w(k, j)$

Hvis vi kan gå innom en annen node så er det korteste vei hvis det er kjappere enn det estimatet vi har

### Slow-apsp
Har kjøretid $O(n^4)$

### Faster-APSP
Bruker ikke vekt matrise men heller 

Vi har $\Theta(n^3lgn)$


### Transitiv lukning
vi går via noe, eller vi kan gå via via for å komme oss samme sted

Transitive-Closuere
Vi har $\Theta(n^3)$

Forgjengere er de som kommer før i korteste veien

### Floyd-Warshall
Bruker en rettet vektet graf
- Tillater negative kanter, men ikke negative sykler
Bruker trekantulikheten på alle kantene for en node
Øker antall noder per sti med den ytterste iterasjonen
$O(n^3)$

### Print-APSP
Tar inn matrisene og printer de korteste veiene
Den er rekursiv og skriver ut alle de korteste veiene
## Forelesning 12
### Max-flow 

#### Lineær program av maxflow
Vi ønsker å maksimere flyten ut av source, (minus flyt inn i source)

Flyten på hver kant må være mindre enn kapasiteten
Flyten inn i en node må være det samme som ut av en node

####  Billigste flyt LP
Kan tolke det som at vi ønsker å minimere kostnaden på flyt
ER et maksimeringsproblem siden i ønsker å maksimere profitt

ferdig med lp!!!


### Flytnett
- er en rettet graf med en kilde og et sluk
	- Det kan være flere men da reduseres det til å være en
- kanter har en kapasitet

- Vi kan ikke ha antiparallelle kanter i et flytnett.
- Ingen løkker (på samme node)

### Flyt
- Kilden kan gi uendelig mye flyt
- Sluket kan ta uendelig mye flyt
- Flyten kan aldri være mer enn kapasiteten
- Flyt kan ikke være negativ

### Max-flow min-cut
Dualitet mellom max-flow og min-cut

### Heltatllsteoremet
Heltallskapasiteter impliserer helttallsflyt når vi finner max-flyt

Ford-Fulkerson finner heltallsflyt

### Bipartitt matching

$V = L\cup{R}$
Vi ønsker å matche så mange i L med så mange i R

Vi sender flyt 1 og har kapasitet på alle kanter på 1
Ford-fulkerson finner max matchign

### Alternde sti & forøkning
Alternerende sti er en sti som går fram og tilbake 
I Bipartitt matching så er en forøkende sti en sti som øker matchingen med 1

### Forøkende sti
Augmenting path på engelsk

Det er en forøkende sti fra kilde til sluk i max-flow
### Restnett
Restnett, Residual network

Er et nettverk der kanter som går 

### Ford-fulkerson
Er en metode for hvordan vi finner max-flyt

Vi reduserer flyt til å lage restnett også traverserer vi til sluket også finner vi en forøkende sti
hvis det ikke finnes en forøkende sti så er vi ferdige

### Edmonds-karp 
Bruker bredde først søk for å finne en forøkende sti i ford-fulkerson
$O(VE^2)$
## Forelesning 13
### NP-kompletthet
NP = Nondeterministically Polynomial

Et problem som alle andre problemer i NP kan reduseres til.
- Å redusere til noe enkelt er nyttig
- å redusere fra noe vanskelig er informativt

Vi ser ikke på løsninger men heller på beslutningsproblem
Vi kan verifisere svarene våre i polynomisk tid

### Flere kompleksitetsklasser

P = polynomisk tid
- Kan løses i $O(n^k)$ tid
NP er verifiserbare i polynomsik tid
NP-hardt er like vanskelig som det i NP
NP-komplette (NPC) problemer
- De er minst like vanskelige som alle andre problemer i NP
- Kan sjekke svaret fort
Co-NP skal også vite om

Vi må redusere fra NPC. 

## Forelesning 14
### NP-komplette problemer
Vi må kjenne til disse problemene

#### Circuit-Sat
Vi har en del kretser og skal finne ut om det kan bli 1

### Sat
Logiske utrykk og finne ut om det kan bli true

### 3-CNF-SAT
Nå er det på en spesifikk form

### Clique
### Vertex cover
### Hamiltonian Cycle
### TSP
Finne en kjappeste vei gjennom alle noder, med vekter
### Subset sum
Finne ut om en sum av subset i en menge er lik t
### 01-Knapsack
Kan løses ganske effektivt med LP

