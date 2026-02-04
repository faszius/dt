---
tags:
  - foliensatz/04
  - cleaned
  - "#MoC"
aliases:
  - boole'sche
  - boolesche
  - Boole'sche Ausdrücke
  - Boole'scher Ausdruck
Related:
  - "[[Operatorpräzedenz]]"
  - "[[Disjunktive Normalform (DNF)]]"
  - "[[Konjunktive Normalform (KNF)]]"
  - "[[Logikminimierung]]"
---

## Boole'sche Gleichungen

- Beschreiben Ausgänge einer kombinatorischen Schaltung als (boole'sche) Funktion der Eingänge
- Spezifikation des funktionalen Verhaltens (ohne zeitliche Information)
- Unter Verwendung elementarer boole'scher Operatoren (sortiert nach Operatorpräzedenz):
  ![[Operatorpräzedenz]]

## Grundlegende Definitionen

- Komplement
	- Boole'sche Variable mit einem Balken (invertiert)
	- $\overline{A}$, $\overline{B}$, $\overline{C}$
- Literal
	- Variable oder ihr Komplement
	- $A$, $\overline{A}$, $B$, $\overline{B}$, $C$, $\overline{C}$
- Implikant
	- Produkt von Literalen
	- $ABC$, $A\overline{C}$, $BC$
- [[Minterm]]
	- Produkt (UND, Konjunktion) über _alle_ Eingangsvariablen
	- $ABC$, $AB\overline{C}$, $\overline{A}BC$
- [[Maxterm]]
	- Summe (ODER, Disjunktion) über _alle_ Eingangsvariablen
	- $(A+\overline{B}+\overline{C})$, $(A+B+\overline{C})$, $(\overline{A}, \overline{B}, \overline{C})$

