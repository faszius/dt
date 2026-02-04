---
tags:
  - foliensatz/08
  - cleaned
Related:
  - "[[Vergleich D-Latch mit D-Flip-Flop]]"
---

## D-Latch

- Wir haben ein Daten-Latch mit Taktsignal (CLK) und Dateneingang (D)
	- $\text{CLK} = 1 \rightarrow$ Zustand auf $D$ setzen (Latch transparent)
	- $\text{CLK} = 0 \rightarrow$ Zustand halten (Latch nicht transparent)
- Ungültiger Zustand am [[SR-Latch]] wird vermieden
- Rückkopplung nur noch im SR-Latch

Darstellung des Gatters:
![[Pasted image 20251203193635.png]]

Aufbau des Gatters:
![[Pasted image 20251203193644.png]]

Wahrheitstabelle:
![[Pasted image 20251203193652.png]]

## Problem des D-Latch

- Periodische Taktsignale sind üblicherweise symmetrisch
	- $0$-Phase und $1$-Phase sind gleich lang
- D-Latch ist Taktphasen-gesteuert
	- Das bedeutet, dass er für die Hälfte der gesamten Zeit transparent ist
	- Sequentielle Schaltungen mit D-Latches sind also für die Hälfte der Zeit kombinatorisch
- Das breite "Abtastfenster" sorgt für Unschärfe
	- Bspw. unklar, ob ein Störimpuls übernommen wurde

![[Pasted image 20251203193913.png]]