---
tags:
  - foliensatz/05
  - cleaned
---

## Konventionen für lesbare Schaltpläne

- Eingänge links (oder oben)
- Ausgänge rechts (oder unten)
- Gatter von links nach rechts (oben nach unten) angeordnet
- Gerade (oder rechtwinklige) Verbindungen
- Keine Schrägen oder Kurven
- 3-armige Kreuzungen gelten implizit als verbunden
- 4-armige Kreuzungen gelten nur bei Markierung (Punkt) als verbunden

![[Screenshot 2025-11-14 at 19.34.32.png]]

## Zweistufige Logik

- Direkte (konstruktive) Umsetzung der disjunktiven Normalform ([[Disjunktive Normalform (DNF)|DNF]])
	- Eingangsliterale: ein Inverter pro Variable (falls benötigt)
	- [[Minterm|Minterme]]: je ein "breites" AND Gatter an passende Literale anschließen
	- Summe: alle Minterme an ein "breites" OR Gatter anschließen
- Gatter mit vielen kleinen Inputs als Bäume kleinerer Gatter
- Jede boole'sche Funktion realisierbar mit Basisgattern
	- AND2
	- OR2
	- NOT

![[Screenshot 2025-11-14 at 19.39.19.png]]

