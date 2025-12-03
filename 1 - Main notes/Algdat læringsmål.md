2025-11-30 12:01

Tags: #algdat #algorithms 

# Algdat læringsmål
## **Overordnede læringsmål**

*  [ ] [X1] Dere skal ha kunnskap om et bredt spekter av etablerte algoritmer og datastrukturer.
*  [x] [X2] Dere skal ha kunnskap om klassiske algoritmiske problemer med kjente effektive løsninger.
*  [x] [X3] Dere skal ha kunnskap om komplekse problemer uten kjente effektive løsninger.
*  [x] [X4] Dere skal kunne analysere algoritmers korrekthet og effektivitet.
*  [x] [X5] Dere skal kunne formulere problemer så de kan løses av algoritmer.
*  [ ] [X6] **!** Dere skal kunne konstruere nye effektive algoritmer.
*  [x] [X7] Dere skal være i stand til å bruke eksisterende algoritmer og programvare på nye problemer.
*  [ ] [X8] Dere skal være i stand til å utvikle nye løsninger på praktiske algoritmiske problemstillinger.

## **Forkunnskaper (Y-mål)**

*  [x] [Y1] Kjenne til begreper rundt monotone funksjoner.
*  [x] [Y2] Kjenne til notasjonene $\lceil x\rceil$, $\lfloor x\rfloor$, $n!$ og $a \bmod n$.
*  [x] [Y3] Vite hva polynomer er.
*  [x] [Y4] Kjenne grunnleggende potensregning.
*  [x] [Y5] Ha noe kunnskap om grenseverdier.
*  [x] [Y6] **!** Være godt kjent med logaritmer med ulike grunntall.
*  [x] [Y7] Kjenne enkel sannsynlighetsregning, indikatorvariable og forventning.
*  [x] [Y8] Ha noe kjennskap til rekkesummer (se også side 16 i dette heftet).
*  [x] [Y9] Beherske helt grunnleggende mengdelære.
*  [x] [Y10] Kjenne grunnleggende terminologi for relasjoner, ordninger og funksjoner.
*  [x] [Y11] Kjenne grunnleggende terminologi for og egenskaper ved grafer og trær.
*  [x] [Y12] Kjenne til enkel kombinatorikk, som permutasjoner og kombinasjoner.
*  [x] [Y13] Forstå hvordan tabeller (arrays), matriser, stakker og køer fungerer.
*  [x] [Y14] Forstå hvordan lenkede lister fungerer.
*  [x] [Y15] **!** Forstå hvordan hashtabeller fungerer.
*  [x] [Y16] Vite at man for statiske datasett kan ha worst-case O(1) for søk (såkalt perfekt hashing).
*  [x] [Y17] Forstå hvordan tabelldobling (array doubling) fungerer.

## **Generelle læringsmål for algoritmer, datastrukturer og problemer (Z-mål)**

Disse målene gjelder gjennom hele semesteret for hver algoritme, datastruktur og problemstilling som dekkes.

**Læringsmål for hver algoritme:**
*  [ ] [Z1] Kjenne den formelle definisjonen av det generelle problemet den løser.
*  [ ] [Z2] Kjenne til eventuelle tilleggskrav den stiller for å være korrekt.
*  [ ] [Z3] Vite hvordan den oppfører seg; kunne utføre algoritmen, trinn for trinn.
*  [ ] [Z4] **!** Forstå korrekthetsbeviset; hvordan og hvorfor virker algoritmen egentlig?.
*  [ ] [Z5] Kjenne til eventuelle styrker eller svakheter, sammenlignet med andre.
*  [ ] [Z6] Kjenne kjøretidene under ulike omstendigheter, og forstå utregningen.

**Læringsmål for hver datastruktur:**
*  [ ] [Z7] Forstå algoritmene (jf. mål Z1–Z6) for de ulike operasjonene på strukturen.
*   [ ] [Z8] Forstå hvordan strukturen representeres i minnet.

**Læringsmål for hvert problem:**
*  [ ] [Z9] Kunne angi presist hva input er.
*  [ ] [Z10] Kunne angi presist hva output er og hvilke egenskaper det må ha.

## **Læringsmål per forelesning**

### **Forelesning 1: Algoritmer og kompleksitet**

*  [x] [A1] Forstå bokas pseudokode-konvensjoner.
*  [x] [A2] Kjenne egenskapene til random-access machine-modellen (RAM).
*  [x] [A3] Kunne definere problem, instans og problemstørrelse.
*  [x] [A4] **!** Kunne definere og bruke asymptotisk notasjon, O, $\Omega$, $\Theta$, o og $\omega$.
*  [x] [A5] **!** Kunne definere best-case, average-case og worst-case.
*  [x] [A6] **!** Forstå at alle av O, $\Omega$, $\Theta$, o og $\omega$ kan beskrive best-, worst- og average-case.
*  [x] [A7] Forstå Insertion-Sort.

### **Forelesning 2: Problemer og reduksjoner**

*  [x] [B1] Forstå definisjonene av **søkeproblemer**, **beslutningsproblemer** og **optimeringsproblemer**.
*  [x] [B2] Forstå ulike typer reduksjoner (Turing, Cook, Levin og Karp), og forholdet mellom dem.
*  [x] [B3] Forstå redusibilitets-relasjonen som relativ vanskegrad.
*  [x] [B4] **!** Forstå **løkkeinvarianter** og **induksjon**.
*  [x] [B5] **!** Forstå **rekursiv dekomponering** og induksjon over delinstanser.
*  [x] [B6] Kjenne til bruk av lineære program for å beskrive problemer.

### **Forelesning 3: Splitt og hersk**

*  [x] [C1] **!** Forstå designmetoden **divide-and-conquer** (splitt og hersk).
*  [x] [C2] Forstå Bisect og Bisect′ (se appendiks D i dette heftet).
*  [x] [C3] Forstå Merge-Sort.
*  [x] [C4] Forstå Quicksort og Randomized-Quicksort.
*  [ ] [C5] **!** Kunne løse rekurrenser med **substitusjon**, **rekursjonstrær** og **masterteoremet**.
*  [ ] [C6] **!** Kunne løse rekurrenser med **iterasjonsmetoden** (se appendiks C i dette heftet).

### **Forelesning 4: Rangering i lineær tid**

*  [x] [D1] **!** Forstå hvorfor sammenligningsbasert sortering har en worst-case på $\Omega(n \lg n)$.
*  [x] [D2] Vite hva en **stabil sorteringsalgoritme** er.
*  [ ] [D3] Forstå Counting-Sort, og hvorfor den er stabil.
*  [ ] [D4] **!** Forstå Radix-Sort, og hvorfor den trenger en stabil subrutine.
*  [ ] [D5] Forstå Bucket-Sort.
*  [ ] [D6] Forstå Randomized-Select.
*  [x] [D7] Kjenne til Select (Inkl. å vite at den kan brukes til å finne de $k$ minste elementene med kjøretid $O(n)$).

### **Forelesning 5: Rotfaste trestrukturer**

*  [x] [E1] **!** Forstå hvordan **hauger** fungerer, inkl. **haugegenskapen** (the heap property), og hvordan de kan brukes som prioritetskøer (Parent, Left, Right, Max-Heapify, Build-Max-Heap, Heapsort, Max-Heap-Insert, Max-Heap-Extract-Max, Max-Heap-Increase-Key, Max-Heap-Maximum. Også tilsvarende for min-heaps, f.eks., Build-Min-Heap og Min-Heap-Extract-Min.).
*  [ ] [E2] Forstå Heapsort.
*  [x] [E3] Forstå hvordan rotfaste trær kan implementeres med noder og pekere (inkl. med pekere til første barn og neste søsken).
*  [x] [E4] **!** Forstå hvordan **binære søketrær** fungerer, inkl. **binær-søketre-egenskapen** (the binary-search-tree property) (Inorder-Tree-Walk, Tree-Search, Iterative-Tree-Search, Tree-Minimum, Tree-Maximum, Tree-Successor, Tree-Predecessor, Tree-Insert, Transplant, Tree-Delete).
*  [x] [E5] Vite at forventet høyde for et tilfeldig binært søketre er $\Theta(\lg n)$.
*  [x] [E6] Vite at det finnes søketrær med garantert høyde på $\Theta(\lg n)$.

### **Forelesning 6: Dynamisk programmering**

*  [ ] [F1] **!** Forstå ideen om en **delinstansgraf**.
*  [x] [F2] **!** Forstå designmetoden **dynamisk programmering**.
*  [x] [F3] **!** Forstå løsning ved **memoisering** (top-down).
*  [x] [F4] Forstå løsning ved **iterasjon** (bottom-up).
*  [x] [F5] Forstå hvordan man rekonstruerer en løsning fra lagrede beslutninger.
*  [x] [F6] Forstå hva **optimal delstruktur** er.
*  [x] [F7] Forstå hva **overlappende delinstanser** er.
*  [ ] [F8] Forstå eksemplene **stavkapping** og **LCS**.
*  [ ] [F9] Forstå løsningen på det **binære ryggsekkproblemet** (appendiks E i dette heftet) (Knapsack, Knapsack′).

### **Forelesning 7: Grådighet**

*  [x] [G1] **!** Forstå designmetoden **grådighet**.
*  [x] [G2] **!** Forstå **grådighetsegenskapen** (the greedy-choice property).
*  [ ] [G3] Forstå eksemplene **aktivitetsutvelgelse** og det **kontinuerlige ryggsekkproblemet**.
*  [x] [G4] Forstå **Huffman** og **Huffman-koder**.

### **Forelesning 8: Traversering av grafer**

*   [x] [H1] Forstå hvordan grafer kan implementeres.
*   [x] [H2] Forstå **BFS**, også for å finne korteste vei uten vekter (Inkl. Print-Path).
*   [x] [H3] Forstå **DFS**, **parentesteoremet** og **hvit-sti-teoremet**.
*   [ ] [H4] Forstå hvordan DFS klassifiserer kanter.
*   [ ] [H5] Forstå Topological-Sort.
*   [x] [H6] Forstå Strongly-Connected-Components.
*   [x] [H7] Forstå hvordan DFS kan implementeres med en stakk.
*   [x] [H8] Forstå hva **traverseringstrær** (som bredde-først- og dybde-først-trær) er.
*   [x] [H9] **!** Forstå traversering med **vilkårlig prioritetskø**.

### **Forelesning 9: Minimale spenntrær**

*  [x] [I1] Forstå skog-implementasjonen av **disjunkte mengder** (Connected-Components, Same-Component, Make-Set, Union, Link, Find-Set).
*  [x] [I2] Vite hva **spenntrær** og **minimale spenntrær** er.
*  [x] [I3] **!** Forstå **Generic-MST**.
*  [x] [I4] Forstå når og hvorfor **lette kanter er trygge kanter**.
*  [x] [I5] Forstå **MST-Kruskal**.
*  [x] [I6] Forstå **MST-Prim**, inkl. kjøretid med Fibonacci-haug.

### **Forelesning 10: Korteste vei fra én til alle**

*  [x] [J1] Forstå ulike varianter av **korteste-vei-** eller **korteste-sti-problemet** (Single-source, single-destination, single-pair, all-pairs).
*  [x] [J2] Forstå strukturen til korteste-vei-problemet.
*  [x] [J3] Forstå at **korteste enkle vei** (simple path) kan eksistere selv om en negativ sykel forhindrer at korteste vei gjør det.
*  [ ] [J4] Forstå at korteste enkle vei kan løses vha. **lengste enkle vei** og omvendt.
*  [ ] [J5] Forstå hvordan man kan representere et **korteste-vei-tre**.
*  [x] [J6] **!** Forstå **kant-oppdatering** (edge relaxation) og **Relax**.
*  [ ] [J7] Forstå ulike egenskaper ved korteste veier og oppdatering (Triangle inequality, upper-bound property, no-path property, convergence property, path-relaxation property, predecessor-subgraph property).
*  [x] [J8] Forstå **Bellman-Ford**.
*  [x] [J9] Forstå **Dag-Shortest-Paths**.
*  [ ] [J10] **!** Forstå kobling mellom Dag-Shortest-Paths og **dynamisk programmering**.
*  [x] [J11] Forstå **Dijkstra**, inkl. kjøretid med Fibonacci-haug.
*  [ ] [J12] Kunne uttrykke korteste-vei-problemet (én til én) som et **lineært program**.

### **Forelesning 11: Korteste vei fra alle til alle**

*  [ ] [K1] Forstå forgjengerstrukturen for alle-til-alle-varianten av korteste-vei-problemet (Print-All-Pairs-Shortest-Path).
*  [ ] [K2] Forstå Slow-APSP og Faster-APSP.
*  [ ] [K3] Forstå **Floyd-Warshall**.
*  [ ] [K4] Forstå **Transitive-Closure**.

### **Forelesning 12: Maksimal flyt**

*  [x] [L1] Kunne definere **flytnett**, **flyt** og **maks-flyt-problemet**.
*  [x] [L2] Kunne håndtere **antiparallelle kanter** og **flere kilder og sluk**.
*  [x] [L3] **!** Kunne definere **restnettet** til et flytnett med en gitt flyt.
*  [x] [L4] Forstå hvordan man kan **oppheve (cancel) flyt**.
*  [x] [L5] Forstå hva en **forøkende sti** (augmenting path) er.
*  [ ] [L6] Forstå hva **snitt**, **snitt-kapasitet** og **minimalt snitt** er.
*  [ ] [L7] **!** Forstå **maks-flyt/min-snitt-teoremet**.
*  [x] [L8] Forstå **Ford-Fulkerson-Method** og **Ford-Fulkerson**.
*  [x] [L9] Forstå **Edmonds-Karp-algoritmen** (Ford-Fulkerson med BFS).
*  [ ] [L10] Forstå hvordan Ford-Fulkerson kan finne et **minimalt snitt**.
*  [x] [L11] Forstå hvordan maks-flyt kan finne en **maksimum bipartitt matching**.
*  [x] [L12] **!** Forstå **heltallsteoremet** (integrality theorem).
*  [x] [L13] **!** Være i stand til å konstruere **reduksjoner til maks-flyt-problemet**.
*  [ ] [L14] Kunne uttrykke maks-flyt og **billigste flyt** (minimum-cost flow) som **lineære program**.

### **Forelesning 13: NP-kompletthet**

*  [x] [M1] Forstå **koding** (encoding) av en instans.
*  [ ] [M2] Forstå hvorfor løsningen på det **binære ryggsekkproblemet** ikke er polynomisk.
*  [ ] [M3] Forstå forskjellen på **konkrete** og **abstrakte problemer**.
*  [x] [M4] Forstå representasjonen av **beslutningsproblemer** som **formelle språk**.
*  [ ] [M5] Forstå definisjonen av klassene **P**, **NP** og **co-NP**.
*  [x] [M6] **!** Forstå definisjonen av **NP-hardhet** og **NP-kompletthet**.
*  [ ] [M7] Forstå forholdet mellom NP-hardhet/NP-kompletthet og ulike problemtyper (Søkeproblemer, beslutningsproblemer og optimeringsproblemer).
*  [ ] [M8] Forstå den konvensjonelle hypotesen om forholdet mellom P, NP og NPC.
*  [ ] [M9] Forstå reduksjon begge veier mellom **optimering** og **terskling**.
*  [x] [M10] Forstå reduksjon begge veier mellom **søk** og **beslutning**.
*  [x] [M11] Forstå beviset for at **CIRCUIT-SAT er NP-komplett**.

### **Forelesning 14: NP-komplette problemer**

*  [x] [N1] **!** Forstå hvordan **NP-kompletthet kan bevises ved én reduksjon**.
*  [ ] [N2] **!** Kjenne de **NP-komplette problemene** CIRCUIT-SAT, SAT, 3-CNF-SAT, CLIQUE, VERTEX-COVER, HAM-CYCLE, TSP og SUBSET-SUM.
*  [x] [N3] Forstå NP-kompletthetsbevisene for disse problemene.
*  [x] [N4] Forstå at det **binære ryggsekkproblemet er NP-hardt**.
*  [x] [N5] Forstå at **lengste-enkle-vei-problemet er NP-hardt**.
*  [x] [N6] Kjenne generelle reduksjonsstrategier og kunne konstruere enkle bevis for NP-hardhet og NP-kompletthet.