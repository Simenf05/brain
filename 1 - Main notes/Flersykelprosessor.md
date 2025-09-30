2025-09-23 11:42

Status:
Tags: #datamaskiner #computers

# Flersykelprosessor

Vi deler opp instruksjonene våre i mindre biter slik at vi kan ta dem 

# Samlebåndarkitektur

1. Instruksjonshenting (IF)
2. Instruksjonsdekoding og registerlesing (ID)
3. Utføring (EX)
4. Minneaksess (MEM)
5. Tilbakeskriving (WB)

### Oppstartskostnad
Det tar tid før den første instruksjonen kommer gjennom samlebåndet.

### Hazards
En fare oppstår når et program kan ikke utføres korrekt siden det manger noe

Klasser av farer:
- Strukturfare: En enhet intruksjonen trenger ikke tilgjengelig
- Datafare: Instruksjonen kan ikke utføres fordi data ikke er tilgjengelig
- Kontrollfare: Vi vet ikke hvilken instruksjon som skal utføres

En avhengighet er en egenskap ved programmet, mens en fare er en avhengighet som påvirker utføringen av programmet på en gitt maskin

#### Hvordan håndtere farer?
- Unngå ressurskonflikter
- Forwarding
- Stalling
- Prediksjon