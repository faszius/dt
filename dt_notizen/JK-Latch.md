---
tags:
  - foliensatz/08
  - cleaned
aliases:
  - JK
---

## JK-Latch

- Wir wollen den ungültigen Zustand $SR$ am SR-Latch verhindern
- Interpretation der freien Eingänge $J$ und $K$
	- $\overline{J} \; \overline{K} \rightarrow$ Zustand halten
	- $\overline{J} \; K \rightarrow$ Zustand auf $0$ zurücksetzen, falls nötig
	- $J \; \overline{K} \rightarrow$ Zustand auf $1$ setzen, falls nötig
	- $J \; K \rightarrow$ Zustand invertieren ("toggle")

Darstellung des Gatters:
![[Pasted image 20251203193353.png]]

Aufbau des Gatters:
![[Pasted image 20251203193402.png]]

Wahrheitstabelle:
![[Pasted image 20251203193412.png]]