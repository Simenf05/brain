# Sketch note: 2025-12-10 17:41

# Læring datamaskin

### Overordnede Læringsmål

 Kategori                            Læringsmål                                                                                                                   Kilde 
- [x]  Kunnskaper (K1)           Kjenne til datamaskiners konstruksjon og virkemåte, inkludert hvordan man oppnår høy effektivitet.                                 
 - [x]  Kunnskaper (K2)           Forstå grensesnittet mellom programvare og maskinvare.                                                                             
 - [x]  Kunnskaper (K3)           Forstå hvordan man bygger enkle og effektive prosessorer, inkludert enkeltsykel, flersykel, og samlebåndsarkitekturer.             
 - [x]  Kunnskaper (K4)           Forstå prinsippene bak hvordan man bygger effektive minnesystemer, inkludert hurtigbuffere og virtuelt minne.                      
 - [x]  Kunnskaper (K5)           Forstå hvordan abstraksjon og struktur benyttes for å oppnå høy effektivitet og til å håndtere kompleksitet i datamaskiner.        
 - [x]  Ferdigheter (F1)          Være i stand til å formulere enkle programmer i assemblykode.                                                                      
 - [x]  Ferdigheter (F2)          Være i stand til å lese blokkdiagrammer.                                                                                           
 - [x]  Ferdigheter (F3)          Kunne relatere blokkdiagrammer på ulike abstraksjonsnivå til hverandre.                                                            
 - [x]  Generell kompetanse (G1)  Forstå den generelle virkemåten til en datamaskin og kunne anvende denne kunnskapen i prosjekter på alle abstraksjonsnivå.         

---

### Spesifikke Læringsmål (etter tema)

#### T1: Introduksjon og ytelse

- [ ]  Kjenne til de 7 datamaskintypene og deres viktigste egenskaper.
- [ ]  Kjenne til de 7 store ideene i datamaskinarkitektur.
- [x]  Kan beskrive størrelser med rett prefiks (for eksempel GB og GiB).
- [x]  Kjenne rollen til applikasjonsprogramvare og systemprogramvare, herunder operativsystemet og kompilatoren.
- [x]  Kan beskrive de fem hovedkomponentene i en datamaskin.
- [x]  Kan forklare prinsippet om **lagrede program**.
- [ ]  Kan gjengi **produksjonsprosessen for integrerte kretser**.
- [x]  Kjenne til de viktigste **ytelsesmetrikkene** i datamaskinarkitektur.
- [x]  Kan forklare forskjellen på **kjøretid og båndbredde** og velge den mest hensiktsmessige for gitte arkitekturoppgaver.
- [x]  Kan forklare **«The Iron Law»** og kan bruke den til å forutsi hvordan endringer i arkitekturen påvirker kjøretid.
- [ ]  Kjenne til hvordan spenning og klokkefrekvens påvirker **effektforbruk og strømforbruk**.
- [x]  Vet hva en **testprogramsamling** er og hvorfor de brukes.
- [x]  Vet hvorfor stort sett alle datamaskiner i dag har mer enn én prosessorkjerne.
- [x]  Kan bruke **Amdahl’s lov** til å analysere ytelsesforbedring i datamaskiner.

#### T2: Instruksjonssett

- [ ]  Kjenner til de **tre designprinsippene for instruksjonssettdesign** og deres motivasjon.
- [x]  Kan oversette fra et høynivåspråk til **assemblyinstruksjoner** (og omvendt).
- [x]  Kan oversette fra assemblyinstruksjoner til **maskinkode** (og omvendt).
- [ ]  Kjenner til **instruksjonsformatene i RISC-V** og kan forklare hvorfor de er definert slik de er.
- [x]  Forstår hvordan instruksjoner lagres i minnet og hvordan dette utnyttes til å implementere **kontrollflyt**.
- [x]  Kan representere **heltall** som binære og heksadesimale tall, og oversette mellom disse og titallsystemet.
- [x]  Kan representere **negative heltall på 2’s komplement form** og oversette mellom dette og titallsystemet.
- [x]  Forstår hvorfor **fortegnsutvidelse** av et tall på 2’s komplement form beholder samme tallverdi.
- [x]  Vite hva **overflyt** er og forstå når det oppstår.
- [x]  Kan utføre **logiske operasjoner** på binære tall, inkludert bitvis AND og OR samt logisk og aritmetisk bitskifting.
- [x]  Vet hvilke oppgaver som skal utføres ved et **funksjonskall** og kan forklare konseptet **kallkonvensjon**.
- [x]  Kjenner **RISC-V minnekartet** (figur 2.13).
- [ ]  Forstår forskjellen på **statiske og dynamiske data**.
- [x]  Kjenner til hvordan **tekst** representeres i en datamaskin.
- [x]  Skal vite hvordan vi håndterer **store konstanter** og (unngår) **lange hopp** (PC-relativ adressering).
- [x]  Skal kunne forklare **RISC-Vs fire adressemodi**.
- [x]  Kan forklare skrittene involvert i **oversettelse og oppstart av programmer** (figur 2.20).

#### T3: Enkeltsykelprosessor (inkl. kombinatorisk logikk og ALU)

LæringsmålKilde
- [x]  Skal kunne forklare begrepene **datasti og kontrollenhet**.
- [x]  Skal kunne forklare mikroarkitekturen til **enkeltsykelprosessoren** (figur 4.21).
- [x]  Skal kunne sette opp rett **kontrollord** for en instruksjon, inkludert korrekt bruk av «don’t care».
- [x]  Skal kunne identifisere **instruksjonstype** fra et kontrollord.
- [x]  Skal kjenne til de logiske portene **AND, OR, og inverter** og deres symboler samt kunne beskrive oppførselen deres med sannhetstabeller.
- [x]  Skal kjenne til symbolene og kunne gjengi sannhetstabellene for **kombinerte logiske porter** (NAND og NOR) og mer avanserte kretser (**multiplekser og dekoder**).
- [x]  Skal kunne oversette mellom **boolske uttrykk** på sum-av-produkt form og sannhetstabeller.
- [ ]  Skal kjenne til konseptet **buss** og notasjonen for adressering av enkeltlinjer i busser.
- [ ]  Skal kunne konstruere en 32-bit **aritmetisk-logisk enhet (ALU)** som kan gjøre addisjon og subtraksjon samt logisk AND og OR og nulldeteksjon (figurene A.5.7 og A.5.8).
- [ ]  Skal kunne utføre **multiplikasjon og divisjon** av binære tall og beskrive hvordan disse implementeres i maskinvare.
- [x]  Skal kunne oppgi fordeler og ulemper med å representere tall i et **«fixed-point» format**.
- [x]  Skal kunne motivere for hvorfor vi trenger **flyttall** og beskrive prinsippene for hvordan addisjon og multiplikasjon med flyttallsverdier utføres i maskinvare.
- [x]  Skal kunne konvertere fra **desimaltall til flyttall** og motsatt.
- [x]  Skal kjenne til hvordan man implementerer **SIMD-instruksjoner** og hva de brukes til.

#### T4: Flersykelprosessor (og sekvensiell logikk)

LæringsmålKilde
- [x]  Skal kunne forklare mikroarkitekturen til en **flersykelprosessor** (figur e.4.5.4).
- [x]  Skal kunne forklare hvorfor kontrollenheten til flersykelprosessoren blir en **tilstandsmaskin**.
- [x]  Skal kunne beskrive sammenhengen mellom kontrollordet til flersykelprosessoren og tilstanden i tilstandsmaskinen.
- [x]  Skal kunne beskrive fordeler og ulemper ved flersykelprosessoren sammenliknet med enkeltsykelprosessoren.
- [ ]  Skal kunne beskrive oppførselen til komponentene **SR-lås, D-lås, og D-vippe**.
- [x]  Skal kunne konstruere **registre og registerfiler** med kombinatoriske og sekvensielle logiske komponenter (figur A.8.8 og figur A.8.9).
- [x]  Skal kunne forklare hva en **tilstandsmaskin** er og beskrive hvordan den implementeres i maskinvare (figur A.10.3).
- [x]  Skal kunne forklare funksjonen til **klokkesignalet** i en datamaskin og begrepet **«kritisk sti»**.

#### T5: Samlebåndsprosessorer

LæringsmålKilde
- [x]  Skal kunne beskrive fordeler og ulemper ved **samlebåndsprosessoren** sammenliknet med flersykelprosessoren og enkeltsykelprosessoren.
- [x]  Skal kunne forklare hvordan **oppstartskostnad og balanse** mellom steg i samlebåndet påvirker ytelse.
- [x]  Skal kunne beskrive forskjellen mellom **avhengigheter og farer** samt gjengi de tre hovedgruppene av farer (**strukturfarer, datafarer, og kontrollfarer**).
- [x]  Skal kjenne til de fire overordnede strategiene for å håndtere farer (**unngåelse, videresending, stans, og prediksjon**).
- [x]  Skal kunne forklare den grunnleggende mikroarkitekturen til **5-stegs samlebåndsprosessoren** (figur 4.43).
- [x]  Skal kunne forklare hvordan **kontroll** implementeres i 5-stegs samlebåndsprosessoren.
- [x]  Skal kunne forklare hvordan **videresending og stans** kan brukes til å håndtere datafarer samt kunne analysere hvordan strategiene påvirker prosessorens ytelse.
- [x]  Skal kunne forklare hvordan **kontrollfarer** kan håndteres med stans og prediksjon samt analysere hvordan strategiene påvirker prosessorens ytelse.
- [x]  Skal kunne forklare begrepene **unntak og avbrudd**, inkludert **presise unntak**.
- [x]  Skal kunne beskrive hvordan presise unntak kan implementeres i 5-stegssamlebåndet.
- [x]  Skal kjenne til prinsippene bak hvordan presise unntak implementeres i prosessorer som utfører instruksjoner **ut-av-rekkefølge**.
- [x]  Skal kunne beskrive hvordan en prosessor utnytter **parallellitet i tid og parallellitet i rom**.
- [ ]  Skal kunne gjenkjenne og beskrive **RAW, WAW og WAR farer** og avhengighetene som skaper dem.
- [ ]  Skal forstå prinsippene bak hvordan **«register renaming»** fjerner WAW og WAR farer.
- [ ]  Skal kjenne til fordeler og ulemper med **«static multi-issue»** prosessorer.
- [ ]  Skal kjenne til prinsippene bak hvordan prosessorer som utfører instruksjoner ut av rekkefølge (**«dynamic multi-issue»**).
- [ ]  Skal kunne forklare begrepet **«speculation»**.

#### T6: Minnesystemet (Hurtigbuffer og Virtuelt Minne)

LæringsmålKilde
- [x]  Skal kunne forklare begrepene **lokalitet i tid og lokalitet i rom** og vite hvorfor lokalitet oppstår.
- [x]  Skal forstå hvordan og hvorfor et **hierarki av minner** kan gi illusjonen av ett stort og raskt minne.
- [x]  Skal kunne forklare begrepene **volatilt og ikke-volatilt** minne samt **statisk og dynamisk** minne.
- [x]  Skal kjenne til **omtrentlig aksesstid og kostnad per bit** for SRAM, DRAM, Flash, og magnetisk disk og forklare hvordan dette påvirker bruk i minnehierarkiet.
- [x]  Skal kunne konstruere et **SRAM minne** fra grunnleggende kombinatoriske og sekvensielle komponenter (figur A.9.3).
- [x]  Skal kunne beskrive prinsippene for hvordan vi konstruerer **DRAM minner** (figur A.9.5 og A.9.6).
- [x]  Skal kunne forklare hvordan **virtuelle adresser oversettes til fysiske adresser**, inkludert arbeidsfordelingen mellom maskinvare og programvare.
- [x]  Skal kunne forklare hvordan et **«Translation Lookaside Buffer (TLB)»** brukes til å implementere rask adresseoversettelse.
- [x]  Skal kunne forklare hvordan **virtuelt minne** kan brukes til å beskytte prosesser fra hverandres minneaksesser.
- [x]  Skal kunne forklare hvordan **sidefeil** håndteres.
- [x]  Skal kunne forklare hva en **virtuell maskin** er.
- [x]  Skal kunne forklare hvordan vi konstruerer et **direktetilordnet hurtigbuffer** (figur 5.10) samt hvordan det kan utvides til å håndtere blokker som består av mer enn ett ord.
- [x]  Skal kunne forklare hvordan **hurtigbuffere** kan integreres i en samlebåndsarkitektur.
- [x]  Skal kjenne til prinsippene for hvordan hurtigbuffere håndterer **skriveoperasjoner**.
- [x]  Skal kunne **beregne** hvordan minneaksesstid påvirker datamaskinens ytelse.
- [x]  Skal kunne **beregne** hvordan treffraten i flernivå hurtigbuffer påvirker den gjennomsnittlige aksesstiden.
- [x]  Skal forstå hvorfor **settassosiative og fullassosiative** hurtigbuffere kan øke treffraten og hvordan de konstrueres (figur 5.18).
- [x]  Skal kjenne til hvordan man på **programvarenivå** kan påvirke treffraten i hurtigbuffere.

#### T7: Parallelle datamaskiner

 Læringsmål                                                                                                                                                                                          Kilde 
 - [x]  Skal kunne forklare hvorfor det er enklere å utnytte **parallellitet mellom uavhengige program** enn innad i ett program.                                                                       
 - [x]  Skal kunne bruke **Amdahls lov** til å analysere skalerbarheten til parallelle programmer.                                                                                                      
 - [x]  Skal kunne forklare **Flynns taksonomi** og kunne gi eksempler på SISD, SIMD, og MIMD maskiner.                                                                                                 
 - [ ]  Skal kunne bruke **Roofline-modellen** og konseptet **operasjonsintensitet** til å analysere hvorvidt en applikasjon er minnebundet eller beregningsbundet.                                     
 - [ ]  Skal kunne beskrive den overordnede arkitekturen til multiprosessorer med **delt minne og distribuert minne** samt kjenne til deres styrker og svakheter.                                       
 - [x]  Skal kunne beskrive den overordnede arkitekturen til en **flerkjerneprosessor** og kunne motivere for hvorfor arkitekturen er som den er.                                                       
 - [ ]  Skal kunne forklare hvorfor **synkronisering** er nødvendig og de grove trekkene i hvordan synkronisering implementeres.                                                                        
 - [x]  Skal kjenne til behovet for å holde hurtigbuffere **koherente** og de grove trekkene i hvordan det løses.                                                                                       
 - [ ]  Skal kunne beskrive **minnekonsistensproblemet** og kjenne til de grove trekkene i hvordan det løses.                                                                                           
 - [ ]  Skal kunne forklare hva en **domene-spesifikk akselerator (DSA)** er og motivere for hvorfor disse kan oppnå høyere ytelse enn mer generelle arkitekturer.                                      
 - [x]  Skal kunne forklare den overordnede arkitekturen til **grafikkprosessorer (GPUer)** samt kunne beskrive programmeringsmodellen som benyttes når man bruker GPUer til generell beregning.        
 - [x]  Skal kunne beskrive likheter og forskjeller mellom **GPUer, vektorprosessorer, og SIMD-instruksjoner**.                                                                                         
 - [x]  Skal kunne forklare hvorfor det er enklere å utnytte parallellitet mellom uavhengige program enn innad i ett program.                                                                           