---
tags:
  - foliensatz/06
  - cleaned
aliases:
  - mehrwertig
---

## Mehrwertige Logik

- Bisher galt:
	- Jeder Schaltungsknoten (außer Eingänge) wird von _genau einem_ Schaltungselement auf $0$ oder $1$ getrieben
	- Axiome der [[Boole'sche Algebra|boole'schen Algebra]] basieren auf $\mathbb{B} = \{0, 1\}$
- Ignoriert wichtige Teile der Realität
	- Wie breiten sich ungültige Spannungen in Schaltung aus?
- Unterscheidung von zwei weiteren Logikwerten neben $0$ und $1$
	- $X$: mehrfach getrieben: fehlerhaft
	- $Z$: ungetrieben/hochohmig (high impedance): gezielt
- Achtung:
	- Nicht mit "Don't Care" ($*$) verwechseln
	- Tatsächliche Spannung _kann_ auch im $0$- oder $1$-Bereich liegen, das Schaltungsdesign stellt dies aber nicht sicher

## X (mehrfach getrieben) bei konkurrierenden Ausgängen

- Mehrere (unabhängige) Treiber für denselben Schaltungsknoten
- Konflikt, sobald Treiber in entgegengesetzte Richtung ziehen
	- Instabil: abhängig von Betriebsspannung, Temperatur, etc.
	- Destruktiv: Kurzschluss verursacht hohen Energieverbrauch
- Fast immer ein Entwurffehler
	- Z.B. doppelte Zuweisung in Hardwarebeschreibung
	- Konflikt-Quelle muss in Simulation leicht nachvollziehbar sein

![[Pasted image 20251121113811.png]]

## Z (ungetrieben/hochohmig) bei Tristate-Buffer

- Zusätzliches Enable-Signal EN an Buffer
	- $EN=1$: Funktion wie normaler Buffer
	- $EN=0$: Ausgang hochohmig (offen, ungetrieben, floating, high-impedance) Z

![[Pasted image 20251121135635.png]]
![[Pasted image 20251121135642.png]]

### Bus mit Tristate-Buffern

- Mehrere Treiber an gemeinsamer Leitung
- Zu jedem Zeitpunkt _genau ein_ aktiver Treiber
- Erlaubt Wechsel der Kommunikationsrichtung

### Tristate-Buffer für Multiplexer

![[Pasted image 20251121135355.png]]

## Mehrwertige Logik in Schaltnetzen

- Resolutionstabellen definieren Ausbreitung von $X$ (mehrfach getrieben) und $Y$ (hochohmig)
- Mehr Konvention (für Simulator) als physikalische Realität

![[Pasted image 20251121135811.png]]

## Hochohmiger Ausgang ($Z$) und dessen _falsche_ Synthese in SV

![[Pasted image 20251121135910.png]]