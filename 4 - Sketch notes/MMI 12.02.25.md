# Sketch note: 2025-02-12 14:12

# MMI 12.02.25
#mmi 

# Konseptuelle- og mentale modeller

## Tre modeller av IT-system
- Designer (designers model)
- User (users model)
- System (system image)

### Designmodellen

#### Høyivås beskrivelse av
- Hvordan et system er organisert
- hvordan systemet virker

### Lese om konseptuell modell

Det brukeren blir eksponert for

- designmetaforen
- Konseptene
	- Hva brukeren kan gjøre med konseptene
	- Konseptene sine attributer
- Relasjonene
- Overførbarheten (mapping)

### Eksempel:
#### AtB
Konsepter:
- Billett
	- Attributter: Reiseform, Type, Gyldighet, Pris, Strekkode, Gyldig sone
	- Operasjoner: Endre reiseform, endre sone, legge til antall billetter, trekke fra antall billetter, kjøpe, vise aktive billetter, vise utløpte billetter
- Mobillett-konto
- Profil

## Visuell fremstilling av konsepter og deres relasjoner (ER-diagram)
#er-diagram
Viser en oversikt over relasjonen mellom alle konseptene i en konseptuell modell. (se powerpoint)

## Hva en [[konseptuell modell]] ikke er
- Ikke brukergrensesnittet til et interaktivt system.
	- Den sier ingenting om [[GUI]] til systemet
- Ikke brukerens mentale modell


## Valg av konseptuell modell

- Den konseptuelle modellen påvirker brukerens forståelse av systemet
	- Hvilke konsepter skal vi ha
	- Hva brukeren kan gjøre med konseptene
- Valg av konseptuell modell innebærer ofte at en må gjøre avveiinger 
	- Enkelhet

### Begynne med den konseptuelle modellen

- Det er smart å starte med den konseptuelle modellen som et skjelett
- Det er ikke brukergrensesnittet 
- Når vi først har skjelettet så kan det lages brukergrensesnitt av det

Det blir fort for mange konsepter hvis vi ikke lager en [[konseptuell modell]]


# Brukerens mentale modell

- Hva en bruker tror om et systems virkemåte og struktur
- Styrer i stor grad hvordan brukeren forsøker å interagere med systemet
- Formes ved å tolke visuell struktur og synlig oppførsel 

### Hva former en mental modell

- Erfaringer fra bruk av et løsning
- Erfaringer fra lignende løsninger
- Metaforer
- Samtaler med andre brukere
- Opplæring og brukermanualer

### Det er lurt å få tilgang til brukeren sin mentale modell
- Brukbarnhetsevalueringer
	- Think-aloud (tenke høyt)
- Intervju
- Oppgaveanalyse sammen med bruker


## Når brukerens mentale modell ikke er egnet

- Brukskvaliteten blir verre
- Kan hjelpe brukeren med å få en bedre opplevese

# System image

### Består av
- Brukergrensesnittet
- Kommuniserer den konseptuelle modellen
- Spesielt spiller designmetaforen en viktig rolle

### Gulf of execution and gulf of evaluation

- Gulf of execution
	- Differansen mellom brukerens mål og hvor godt systemet kommuniserer hvordan målet skal nås
- Gulf of evaluation
	- Hvor godt systemet formidler tilstanden
		- Hvis du kjøper en billett men ikke skjønner om du har kjøpt den



# Designmetaforer
## Hva er en metafor
Et blomstrende språk som man vanligvis finner i poesi eller kioskromaner
- NEI!
Det meste av vår virkelighetsoppfattelse
Handler om hvordan vi tenker på ting

### Tids-metaforer
- Klokke
- Tidsur
- Kalender

Hva er måten vi snakker om tid
Vi sparer den, bruker den opp, for mye eller for lite

#### Metaforers funksjon i [[GUI]] 
Metaforer burde bidra til å kommunisere
Fordeler og ulemper med designmetaforer

#### Fordeler:
- Vi kan hjelpe dem med å tenke på systemet slik de skal
#### Ulemper:
- Ting kan forsvinner når ting bryter med metaforen
- Det kan bli for komplisert hvis vi følger alt i den fysiske verden

Viktig å velge en metafor som er relevant
En metafor kan gå ut på dato hvis den ikke er moderne nok.
