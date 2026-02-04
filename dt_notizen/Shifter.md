---
tags:
  - foliensatz/07
  - cleaned
aliases:
  - Shift
---

## Shifter

- Einen Shifter können wir benutzen um $A$ um $B$ Stellen nach links/rechts zu verschieben
- Es gibt verschiedene Strategien zum Auffüllen der freuen Stellen (die Beispiele unten sind für B=1):
	- _Logischer_ Rechts- oder Linksshift: Auffüllen mit Nullen
	- _Umlaufender_ Rechts- oder Linksshift: Auffüllen mit den aus der anderen Seite herausfallenden Bits (Rotation)
	- _Arithmetischer_ Rechtsshift: Auffüllen mit Vorzeichen des als Zweierkomplement interpretierten Dateneingangs (entspricht Division durch $2^B$)
	- _Arithmetischer_ Linksshift: Auffüllen mit Nullen (entspricht Multiplikation mit $2^B$)

![[Pasted image 20251128134814.png]]

### Barrel-Shifter

So könnte die physische Umsetzung eines Rechtsshifts aussehen:

![[Pasted image 20251128134904.png]]

### Arithmetische Shifter als Multiplizierer und Dividierer 

- Arithmetischer Linksshift um $n$ Stellen multipliziert den Zahlenwert mit $2^n$
	- $0001_2 <<< 3 = 01000_2 = 1 \cdot 2^3 = 8$
	- $11101_2 <<< 2 = 10100_2 = -3 \cdot 2^2 = -12$
- Multiplikation mit Konstanten kann aus arithmetischen Linksshifts und Additionen zusammengesetzt werden
	- $a \cdot 6 = a \cdot 110_2 = (a <<< 2) + (a <<< 1)$
- Arithmetischer Rechtsshift um $n$ Stellen dividiert den Zahlenwert durch $2^n$
	- $010000_2 >>>> 4 = 000001_2 = 16/2^4 = 1$
	- $100000_2 >>> 2 = 111000_2 = -32/2^2 = -8$
