---
tags:
  - foliensatz/12
  - cleaned
aliases:
  - PLA
  - Programmable Logic Array
---

## Programmable Logic Array (PLA)

- Realisiert einfache [[Kombinatorische Logik|kombinatorische Logik]] mithilfe von Sum-of-Products ([[Disjunktive Normalform (DNF)|DNF]])
- Zweistufige Logik mit programmierbaren Schaltern in Eingabefeld (links) und Ausgabefeld (rechts)
- Günstigere Varianten:
	- Programmable ROM:
	  nur Ausgabefeld programmierbar
	- Programmable Array Logic (PAL):
	  nur Eingabefeld programmierbar

![[Pasted image 20260124124912.png]]

## Beispiel

Wir wollen folgende Funktionen in einem PLA umsetzen:
- $Y_1 = AB + \overline{A}B$
- $Y_2 = AB + A \overline{B}$

![[Pasted image 20260124125118.png]]

Wir modifizieren das Eingabefeld also so, dass wir einmal $AB$, $\overline{A}B$ und $A\overline{B}$ haben. Dann modifizieren wir das Ausgabefeld so, dass $Y_1$ einmal $AB$ und $\overline{A}B$ verodert, und dass $Y_2$ einmal $AB$ und $A\overline{B}$ verodert.

