---
tags:
  - foliensatz/06
  - foliensatz/05
  - cleaned
  - "#MoC"
---

## Beispiele für Verfahren zur Logikminimierung

- Algebraisch:
	- Umformen nach Axiomen/Theoremen ([[Boole'sche Algebra|boole'sche Algebra]]) 
- Grafisch:
	- [[Karnaugh Diagramme]]
- [[Algorithmische Logikminimierung]]:
	- Exakt: Quine-McCluskey
	- Heuristisch: Espresso

$\Rightarrow$ minimiere Anzahl der zur Darstellung einer Funktion notwendigen Implikanten

## Verwendbarkeit der Verfahren

- Grafische Verfahren:
	- Für viele (> 6) Eingänge nicht mehr praktikabel
	- Keine Optimierung zwischen Ausdrücken für mehrere Ausgänge
- Quine-McCluskey-Methode
	- Berechnet zunächst _alle_ möglichen Implikanten
	- Ermittelt _danach_ minimale Teilmenge für vollständige Überdeckung
	- Rechenzeit steigt exponentiell in der Anzahl der Eingänge
- Für wirklich große Probleme (> 50 Variablen) nur Heuristiken sinnvoll
	- Geringere Laufzeitkomplexität
	- Geringere Lösungsqualität

