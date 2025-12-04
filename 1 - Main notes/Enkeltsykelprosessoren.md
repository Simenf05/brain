2025-09-09 10:21

Status:
Tags: #computers #datamaskiner #processor

# Enkeltsykelprosessoren
Er den enkleste prosessoren vi kan lage, og den bruker en sykel på samtlige instruksjoner. 

### Hva er det prosessoren kunne gjøre?
- Alle instruksjonene våre må:
	- Hente instruksjon i minnet basssert på PC
	- Lese minst ett register
- Vi må også kunne:
	- Skrive maksimalt et register
	- Lese og skrive minne
	- Endre PC

### Hvordan lager vi en enkeltsykelprosessor?
Vi må støtte:
- lw, sw, add, sub, and, or, beq

![[Pasted image 20251204103011.png]]

The concept of the single-cycle-processor is a simple model of how a computer could be designed. It is designed mostly for education, and is not practical for real world use. Every instruction running on the machine is suppose to happen within a single cycle. This is good because that can keep the [[cycles per instruction]] at a constant 1, but is not realistic for more complex machines. Other strategies can achieve even better performance, and division prove to be hard to execute within one cycle. Therefore this processor only implements addition and subtraction and basic branching and memory management. 

## Datapaths
