---
tags:
  - foliensatz/03
  - cleaned
---

## Binärwerte als Spannungspegel

- Wir definieren Spannungspegel für die Werte $0$ und $1$
	- Logikpegel (logic levels)
- Beispiel:
	- $0V \mapsto 0$ (Erde, GND, $V_{SS}$ "Voltage Source Source")\
	- $5V \mapsto 1$ (Versorgungsspannung, $V_{DD}$ "Voltage Drain Drain")
- Aber: reale Spannungspegel unterliegen Rauschen
	- Temperaturunabhängige Widerstände
	- Instabile Betriebsspannungen
	- Übersprechen zwischen benachbarten Leitungen

## Beispiel für Rauschen

![[Screenshot 2025-10-28 at 10.41.07.png]]

- Ausgang eines Gatters ("Treiber") treibt Ausgangsleitung auf $5V$
- Lange Leitung zum nächsten Gatter ("Empfänger") hat hohen Widerstand
- Spannungsabfall bspw. $0,5V$
- Empfänger sieht nur $4,5V$
- Ist das noch eine $1$?

## Binärwerte als Spannungsbereiche

- Definiere Spannungsbereiche für die Werte $0$ und $1$
- Steigere Robustheit durch unterschiedliche Bereiche für Ein-/Ausgänge
	- $V_{OH}$: kleinste Spannung, die ein Treiber als $1$ ausgibt ("Voltage Output High")
	- $V_{IH}$: kleinste Spannung, die ein Empfänger als $1$ interpretiert ("Voltage Input High")
	- $V_{IL}$: größte Spannung, die ein Empfänger als $0$ interpretiert ("Voltage Input High")
	- $V_{OL}$: größte Spannung, die ein Treiber als $0$ ausgibt ("Voltage Output Low")

### Störabstände

![[Screenshot 2025-10-28 at 10.43.53.png]]

- Oberer Störabstand $NM_H = V_{OH} - V_{IH}$ ("Noise Margin High")
- Unterer Störabstand $NM_L = V_{IL} - V_{OL}$ ("Noise Margin Low")

### Gleichstrom-Transferkurve

![[Screenshot 2025-10-28 at 10.45.54.png]]

- Ein idealer Buffer gibt $0V$ aus, wenn er eine Spannung zwischen $0V$ und $\frac{V_{DD}}{2}$ bekommt, und gibt $5V$ aus, wenn er eine Spannung zwischen $\frac{V_{DD}}{2}$ und $V_{DD}$ bekommt
- Ein realer Buffer funktioniert nicht so gut - wenn er eine Spannung zwischen $0V$ und $V_{IL}$ (wobei $V_{IL}$ < $\frac{V_{DD}}{2}$) bekommt, gibt er eine Spannung zwischen $0V$ und $V_{OL}$ aus, je nach dem, wie hoch die Eingangsspannung ist
- Wenn er eine Spannung zwischen $V_{IH}$ und $V_{DD}$ (wobei $V_{IH}$ > $\frac{V_{DD}}{2}$) bekommt, gibt er eine Spannung zwischen $V_{OH}$ und $V_{DD}$ aus, je nach dem, wie hoch die Eingangsspannung ist
- So gibt der Buffer zum einen selten eine perfekte Spannung von $0V$ oder $5V$ aus, und es gibt einen kleinen Spannungsbereich zwischen $V_{IL}$ und $V_{OH}$, in dem sich das Verhalten des Buffers nicht bestimmen lässt

![[Screenshot 2025-10-28 at 11.34.45.png]]

## Absenken der Versorgungsspannung $V_{DD}$

- $V_{DD} = 5V$ in den 1970er-90er Jahren
- Verbesserte Chip-Fertigungstechnologien erfordern/ermöglichen Absenkung
	- Hohe Spannungen würden immer kleinere Transistoren beschädigen
	- Energiebedarf reduzieren
	- $3,3V \rightarrow 2,5V \rightarrow 1,8V \rightarrow 1,5V \rightarrow 1,2V \rightarrow 1,0V$