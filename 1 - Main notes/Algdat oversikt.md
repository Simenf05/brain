2025-11-30 13:06

Tags:

# Algdat oversikt



# **Oversikt over Algoritmer og Metoder i Pensumheftet**

Dette notatet gir en strukturert oversikt over sentrale algoritmer, datastrukturer og designmetoder som dekkes i pensumheftet, inkludert deres kjøretider og viktigste egenskaper, basert på kildematerialet.

## **I. Grunnleggende Algoritmer og Kompleksitet**

| Algoritme / Metode       | Kjøretid (Worst-Case)          | Antagelser / Relevant Info                                                                                                                                                                                                                      |
| :----------------------- | :----------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Insertion Sort**       | $\Theta(n^2)$                  | Bruker en inkrementell tilnærming. Rask for små inputstørrelser. Beste tilfelle er $\Theta(n)$. Sorterer *in place* (krever kun konstant ekstra lagringsplass).                                                                                 |
| **RAM-modellen**         | N/A                            | Antar én-prosessor, sekvensiell instruksjonsutførelse. Hver instruksjon/dataaksess tar konstant tid.                                                                                                                                            |
| **Asymptotisk Notasjon** | $O, \Omega, \Theta, o, \omega$ | Brukes for å beskrive vekstraten av kjøretiden, der lavere ordens ledd og koeffisienter ignoreres. Alle notasjonene kan brukes til å beskrive best-, worst- og average-case.                                                                    |
| **Rekurrenser**          | N/A                            | Beskriver kjøretiden til rekursive algoritmer. Kan løses med **substitusjonsmetoden** (gjette og bevise), **rekursjonstrær** (generere et gjett), **masterteoremet** (kokebok-metode for $T(n) = aT(n/b) + f(n)$), eller **iterasjonsmetoden**. |

## **II. Sortering og Utvelgelse**

| Algoritme / Metode           | Kjøretid                                   | Antagelser / Relevant Info                                                                                                             |
| :--------------------------- | :----------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| **Comparison-Based Sorting** | $\Omega(n \lg n)$ (Worst-Case Lower Bound) | Gjelder for sorteringsalgoritmer som kun er basert på sammenligning (f.eks. $x \le y$).                                                |
| **Merge Sort**               | $\Theta(n \lg n)$                          | Designmetode: Splitt og hersk. Gjennomsnittlig og verste tilfelle er $\Theta(n \lg n)$. Krever ekstra minne, opererer ikke *in place*. |
| **Quicksort**                | $\Theta(n^2)$ (Worst-Case)                 | Designmetode: Splitt og hersk. **Forventet** kjøretid er $\Theta(n \lg n)$. Sorterer *in place*.                                       |
| **Heapsort**                 | $O(n \lg n)$                               | Bruker en Max-Heap (eller Min-Heap). $O(n \lg n)$ i verste tilfelle.                                                                   |
| **Counting Sort**            | $\Theta(k + n)$                            | Lineær tid, antar at elementene er heltall i et område $1$ til $k$. Er en **stabil** sorteringsalgoritme.                              |
| **Radix Sort**               | $\Theta(d(n + k))$                         | Lineær tid hvis Counting Sort brukes som stabil subrutine. $d$ er antall siffer/pass.                                                  |
| **Bucket Sort**              | $\Theta(n^2)$ (Worst-Case)                 | $\Theta(n)$ i gjennomsnittlig tilfelle.                                                                                                |
| **Randomized-Select**        | $O(n)$ (Expected)                          | Finner $i$-te ordens statistikk (element) i forventet lineær tid.                                                                      |
| **Select (Deterministic)**   | $O(n)$ (Worst-Case)                        | Kan brukes til å finne de $k$ minste elementene med kjøretid $O(n)$.                                                                   |

## **III. Datastrukturer**

| Datastruktur                                     | Sentrale Operasjoner (Eksempler)      | Kjøretid (Worst-Case)                                    | Relevant Info                                                                                                                                                                                                  |
| :----------------------------------------------- | :------------------------------------ | :------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Heaps** (Hauger)                               | Max-Heap-Insert, Max-Heap-Extract-Max | $O(\lg n)$                                               | Implementerer prioritetskøer. Bygger på **haugegenskapen** (the heap property).                                                                                                                                |
| **Binary Search Trees (BST)**                    | Tree-Search, Tree-Insert, Tree-Delete | $O(h)$                                                   | $h$ er høyden på treet. Følger **binær-søketre-egenskapen**. Forventet høyde er $\Theta(\lg n)$ for et tilfeldig tre.                                                                                          |
| **Disjoint Sets Forest** (Skog-implementasjonen) | MAKE-SET, UNION, FIND-SET             | $O(m \cdot \alpha(n))$ for en sekvens av $m$ operasjoner | Brukes for å håndtere disjunkte mengder (f.eks. i Kruskal). Bruker Union by Rank og Path Compression. $\alpha(n)$ er den invers-Ackermann funksjonen, som vokser ekstremt sakte (i praksis en liten konstant). |
| **Hash Tables** (Hashtabeller)                   | INSERT, SEARCH, DELETE                | $O(1 + \alpha)$ (Expected Average)                       | $\alpha$ er lastfaktoren $n/m$. Worst-case er $\Theta(n)$ (hvis alle kolliderer). Kan gi $O(1)$ *worst-case* for søk for statiske datasett (perfekt hashing).                                                  |

## **IV. Designmetoder: Dynamisk Programmering og Grådighet**

| Metode / Algoritme               | Kjøretid                        | Egenskaper og Kontekst                                                                                                                                                            |
| :------------------------------- | :------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dynamisk Programmering (DP)**  | Variabel                        | Krever **optimal delstruktur** og **overlappende delinstanser**. Bruker **memoisering** (top-down) eller **iterasjon** (bottom-up). Delinstansene danner en rettet asyklisk graf. |
| **Binary Knapsack (DP-løsning)** | $\Theta(nW)$ (Pseudopolynomisk) | Løser det binære ryggsekkproblemet. Kjøretiden er eksponentiell i inputstørrelsen ($\lg W$). Problemet er NP-hardt.                                                               |
| **Grådighet**                    | Ofte rask                       | Består av lokalt optimale valg. Krever **grådighetsegenskapen** (greedy-choice property) og **optimal delstruktur**.                                                              |
| **Huffman Coding**               | Avhenger av implementering      | Grådig algoritme som konstruerer optimale prefiks-frie koder.                                                                                                                     |

## **V. Grafalgoritmer**

### **Traversering**

| Algoritme                               | Kjøretid        | Formål / Metode                                                                                                                                |
| :-------------------------------------- | :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------- |
| **Breadth-First Search (BFS)**          | $O(V + E)$      | Finner korteste vei i uvektede grafer (antall kanter). Bruker FIFO-kø.                                                                         |
| **Depth-First Search (DFS)**            | $\Theta(V + E)$ | Utforsker så dypt som mulig. Gir tidsstempler ($d/f$) og kan klassifisere kanter (tre, tilbake, fremover, kryss). Kan implementeres med stakk. |
| **Topological Sort**                    | $O(V + E)$      | Lineær sortering av noder i en DAG (Directed Acyclic Graph). Basert på synkende finish-tid fra DFS.                                            |
| **Strongly Connected Components (SCC)** | $\Theta(V + E)$ | Dekomponerer en graf. Bruker to DFS-kjøringer (først på $G$, deretter på $G^T$).                                                               |

### **Minimale Spenntrær (MST)**

| Algoritme       | Kjøretid                        | Antagelser / Metode                                                                                                                                 |
| :-------------- | :------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------- |
| **MST-Kruskal** | $O(E \lg V)$ eller $O(E \lg E)$ | Grådig. Legger til den letteste kanten som ikke skaper en sykel. Bruker Disjoint-Set (Union/Find).                                                  |
| **MST-Prim**    | $O(E + V \lg V)$ (Fib. Heap)    | Grådig. Vokser et tre fra en startnode. Bruker Min-Priority Queue (Fibonacci Heap eller Binary Heap). O($V^2$) med adjacencymatrise-implementasjon. |

### **Korteste Veier (Shortest Paths)**

| Algoritme                 | Kjøretid                     | Antagelser / Metode                                                                                                                |
| :------------------------ | :--------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| **Relaxation**            | $O(1)$                       | Grunnleggende operasjon for å oppdatere korteste-vei-estimater.                                                                    |
| **Bellman-Ford**          | $O(VE)$                      | Håndterer negative kantvekter. Returnerer FALSE hvis en negativ sykel er nådd fra kilden.                                          |
| **DAG-Shortest-Paths**    | $O(V + E)$                   | Raskest mulig, men krever en Directed Acyclic Graph (DAG) . Utføres etter topologisk sortering. Kobles til dynamisk programmering. |
| **Dijkstra**              | $O(E + V \lg V)$ (Fib. Heap) | Krever ikke-negative kantvekter. Grådig, bruker Min-Priority Queue. $O(E \lg V)$ med binær heap.                                   |
| **Floyd-Warshall (APSP)** | $\Theta(V^3)$                | Dynamisk programmering. Finner korteste vei mellom alle par. Håndterer negative vekter, men oppdager negative sykler.              |
| **Transitive-Closure**    | $\Theta(n^3)$                | Finner gjennomløp i en graf ved å erstatte min og + med OR og AND i Floyd-Warshall.                                                |
| **Faster-APSP**           | $\Theta(V^3 \lg V)$          | Basert på matrisemultiplikasjon (gjentatt kvadrering).                                                                             |

### **Maksimal Flyt**

| Metode / Algoritme           | Kjøretid  | Antagelser / Relevant Info                                                                                                                             |
| :--------------------------- | :-------- | :----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ford-Fulkerson Method**    | Variabel  | Iterativ metode som finner og øker flyten langs **forøkende stier** (augmenting paths) i **restnettet**. Oppheving (cancellation) av flyt er sentralt. |
| **Edmonds-Karp Algorithm**   | $O(VE^2)$ | En implementasjon av Ford-Fulkerson som bruker BFS for å finne forøkende stier.                                                                        |
| **Max-Flow Min-Cut Theorem** | N/A       | Verdien av maksimal flyt er lik kapasiteten til minimalt snitt.                                                                                        |
| **Integrality Theorem**      | N/A       | Hvis kapasitetene er heltall, kan maks flyt bli representert av heltallsverdier.                                                                       |

## **VI. NP-Kompletthet og String Matching (Utvalgt)**

| Konsept / Problem            | Kjøretid (Løsning)             | Kompleksitet / Vanskegrad                                                                                                                                                        |
| :--------------------------- | :----------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **P-klasse**                 | Polynomisk tid                 | Beslutningsproblemer løst i polynomisk tid.                                                                                                                                      |
| **NP-klasse**                | N/A                            | Beslutningsproblemer med vitner (sertifikater) som kan verifiseres i polynomisk tid.                                                                                             |
| **NP-hardhet**               | N/A                            | Et problem $X$ er NP-hardt hvis alle problemer i NP kan reduseres til $X$ i polynomisk tid (via Levin-reduksjoner for søkeproblemer, Karp-reduksjoner for beslutningsproblemer). |
| **NP-kompletthet (NPC)**     | Ukjent (Trolig ikke P)         | Problemer som er både i NP og NP-harde. De vanskeligste problemene i NP.                                                                                                         |
| **Bevis for NP-kompletthet** | N/A                            | Bevises ved å redusere fra et kjent NP-komplett problem $X$ **til** det nye problemet $Y$ (dvs. $X \le_P Y$).                                                                    |
| **Kjente NPC Problemer**     | N/A                            | CIRCUIT-SAT, SAT, 3-CNF-SAT, CLIQUE, VERTEX-COVER, HAM-CYCLE, TSP, SUBSET-SUM.                                                                                                   |
| **Binært Ryggsekkproblem**   | N/A                            | NP-hardt.                                                                                                                                                                        |
| **Naiv String Matching**     | $O((n - m + 1)m)$              | Enkel, men ineffektiv i verste fall. $n$ er tekstlengde, $m$ er mønsterlengde.                                                                                                   |
| **Rabin-Karp Algorithm**     | $O((n - m + 1)m)$ (Worst-Case) | Basert på hashing modulo $q$. Forventet kjøretid er $O(n+m)$ hvis antall gyldige treff er lite og $q$ er tilstrekkelig stor.                                                     |
| **Knuth-Morris-Pratt (KMP)** | $\Theta(n)$                    | Lineær matchingstid. Krever $\Theta(m)$ preprocessingtid for å beregne $\pi$-funksjonen (som tilsvarer å unngå eksplisitt beregning av $\delta$).                                |