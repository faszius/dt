---
tags:
  - foliensatz/06
  - cleaned
---

## Quine-McCluskey

- Quine-McCluskey-Methode
	- Berechnet zunächst _alle_ möglichen Implikanten
	- Ermittelt _danach_ minimale Teilmenge für vollständige Überdeckung
	- Rechenzeit steigt exponentiell in der Anzahl der Eingänge

## Espresso-Heuristik

- Details des Algorithmus' hier nicht relevant

### Minimalbeispiel

![[Pasted image 20251121105034.png]]

### Dateiformat

- Jede Zeile beschreibt einen Implikanten mit $n_i$ Zeichen...
	- `0` Eingang negiert im Implikanten
	- `1` Eingang nicht-negiert im Implikanten
	- `-` Eingang nicht im Implikanten (kein Minterm)
- .... und $n_o$ Ausgangsfunktionen mit je einem Zeichen
	- `0` Implikant im off set des Ausgangs (optional)
	- `1` Implikant im on set des Ausgangs
	- `-` Implikant im on set _oder_ off set des Ausgangs (Don't Care)

### Anwendungsbeispiel

- (Typ.) vier Eingänge für dargestellte Ziffer
- Sieben _unabhängig_ schaltbare Segmente $S_0, \ldots, S_6$
- Jedes Segment nur für bestimmte Zeichen aktiv

![[Pasted image 20251121105506.png]]

### 7-Segment Anzeige

![[Pasted image 20251121105523.png]]

#### EIngabedateien

![[Pasted image 20251121105552.png]]

#### Ausgabedateien

![[Pasted image 20251121105619.png]]

