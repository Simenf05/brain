2025-08-29 09:23

Status:
Tags: #algdat #algorithms 

# Algoritmiske problemtyper

Problemer forteller oss hva vi ønsker som en løsning. Et generelt problem er en familie med spesifikke problemer. 

Gitt $R \subseteq \{0, 1\}^*\bigtimes{\{0, 1\}^*}$, er det flere ting vi kan
ønske å gjøre. For hver $x \in \{0, 1\}^*$ kan vi f.eks.
1. Prøve å finne en y slik at (x, y) ↓ R;
	- Dette kalles søkeproblem
	- Ofte å finne noe
2. For en gitt y, sjekke om (x, y) ↓ R;
	- Dette kalles verifiseringsproblem
	- Sjekke om en input og output er korrekt
3. Finne ut om y finnes, slik at (x, y) ↓ R.
	- Besluttningsproblem
	- Får inn en bitstreng og svaret er enten $True$ eller $False$
	- Sjekke om det finnes

### Eksempel:

Å sjekke om en sekvens er sortert eller ikke det gjøres trivielt i lineær tid. Dette er et verifiseringsproblem, og 


### Reduksjoner
#reduksjoner #orakel #reductions

En reduksjon er å forenkle et problem. Kan være for å finne unike i en array så sorterer vi arrayen først. 

Hvis det brukes TODO så kan det bety at det er en reduksjon, siden da har vi ofte gjort andre steg for å forenkle problemet. En hypotetisk subrutine kaller vi et orakel. 

```
SOLVE-X(args)
	do some work to reduce to Y
	// TODO: Solve problem Y
```

Her er TODO et orakel som vi antar at vi har. Da har vi redusert problemet.


#### Cook reduksjoner
Det er en Turing reduksjon med polynomisk kjøretid. Det vil si $O(n^k)$. 
Brukes i alt mulig
#### Levin reduksjon 
Levin reduksjon er når vi kun bruker orakelet en gang. I cook så kan det være flere, men her er det kun en gang. Det skal vi fokusere mer på senere. 
Brukes for søkeproblemer. 
#### Karp reduksjon
Karp reduksjoner gjelder som regel for besluttningsproblemer. Det vil si at vi ikke trenger å gjøre det tilbake til X etter vi har gjort Y. 
Den første reduksjonen i Levin reduksjon er en Karp reduksjon.

