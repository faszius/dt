---
tags:
  - foliensatz/08
  - cleaned
aliases:
  - SR
---

## SR-Latch

- [[Bistabile Grundschaltung]] mit NOR statt NOT
- NOR: Ausgang $0$ wenn eine der Inputs $1$ ist
- Interpretation der freien Eingänge $S$ und $R$
	- $\overline{S} \; \overline{R} \rightarrow$ Zustand halten ("latch" = verriegeln)
	- $\overline{S} \; R \rightarrow$ Zustand auf $0$ zurücksetzen ("reset" $R$)
	- $S \; \overline{R} \rightarrow$ Zustand auf $0$ zurücksetzen ("set" $S$)
	- $S \; R \rightarrow$ ungültiger Zustand ($Q = \overline{Q} = 0$)

Darstellung des Gatters:
![[Pasted image 20251203192809.png]]

Aufbau des Gatters:
![[Pasted image 20251203192820.png]]

Wahrheitstabelle:
![[Pasted image 20251203192838.png]]