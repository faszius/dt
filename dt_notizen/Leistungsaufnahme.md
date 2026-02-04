---
tags:
  - foliensatz/03
  - cleaned
---

## Leistungsaufnahme

- Alternative Begriffe: Leistungsumsatz, Leistungsverbrauch
- Leistung = Energieverbrauch pro Zeiteinheit
- Zwei Arten der Leistungsaufnahme
	- Statische Leistungsaufnahme
	- Dynamische Leistungsaufnahme

## Statische Leistungsaufnahme

- Leistungsbedarf wenn kein Gatter schaltet
- Verursacht durch Leckstrom $I_{DD}$
	- Immer kleinere Transistoren schalten nicht mehr vollständig ab
	- Pseudo-nMOS, ...
- Statische Leistungsaufnahme ist also $P_{\text{static}} = I_{DD} \cdot V_{DD}$ 

## Dynamische Leistungsaufnahme

- Aufladen der Gate-Kapazität $C$ von $0A$ auf $Q = C \cdot V_{DD}$
- Schaltung wird mit Frequenz $f$ betrieben 
- Transistoren schalten $f$-mal pro Sekunde
- Nur die Hälfte davon sind Aufladungen
- $I = \frac{Q}{t} = Q \frac{f}{2} = C \cdot V_{DD} \frac{f}{2}$
- Dynamische Leistungsaufnahme ist:
  $P_{\text{dynamic}} = I \cdot V = (C \cdot V_{DD} \cdot \frac{f}{2})(V_{DD}) = \frac{1}{2}C \cdot V^2_{DD} \cdot f$ 

### Beispiel Leistungsaufnahme

- Abschätzen der Leistungsaufnahme für einen Netbook-Prozessor
	- Versorgungsspannung
	  $V_{DD} = 1,2V$
	- Taktfrequenz
	  $f = 1 GHz$
	- $\sum$ Transistorkapazitäten
	  $C = 20 nF$
	- $\sum$ Leckströme
	  $I_{DD} = 20 mA$

$$\begin{align*}P & = P_{\text{static}} + P_{\text{dynamic}} \\ & = I_{DD} \cdot V_{DD} + \frac{1}{2} \cdot C \cdot V^2_{DD} \cdot f \\ & = 24 mW + 14,4 W \end{align*}$$
