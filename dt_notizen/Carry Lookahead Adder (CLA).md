---
tags:
  - foliensatz/08
  - cleaned
aliases:
  - CLA
---

## Motivation

Wir betrachten als Beispiel folgende Addition:
![[Pasted image 20251203182733.png]]

Wir erkennen folgendes:
- Für $A_i B_i = 1$ ist $C_i = 1$ unabhängig von $C_{i-1}$
	- Bedeutet: wir können für jede Spalte berechnen, ob sie einen Übertrag generiert, unabhängig von der Spalte davor
	- Das nennen wir die "generate"-Flag
- Für $A_I + B_i = 1$ ist $C_i = 1$ wenn $C_{i-1} = 1$
- Für $A_i + B_i = 0$ ist $C_i=0$ unabhängig von $C_{i-1}$
	- Bedeutet: wir können für jede Spalte berechnen, ob sie einen Übertrag aus der vorigen Spalte in die nächste Spalte weiterleiten würde
	- Das nennen wir die "propagate"-Flag

## Generate und Propagate pro Spalte

- So können wir also für jede Spalte einfach ausrechnen, ob sie einen Übertrag wirft:
	- Generate-Flag für Spalte $i$: $G_i = A_i B_i$
	- Propagate-Flag für Spalte $i$: $P_i = A_i + B_i$
	- Übertrag aus Spalte $i$: $C_i = G_i + P_i C_{i-1}$
- Bedeutet eine Spalte gibt einen Übertrag, wenn sie einen generiert oder aus der vorigen Spalte weiterleitet
- Bei naiver Verwendung davon (links) haben wir keinen Vorteil gegenüber [[Addierer|Volladdierern]] (rechts): ![[Pasted image 20251203183730.png]]

## Generate und Propagate über $k$ Spalten

- Generate- und Propagate-Flags können über mehrere Spalten kombiniert werden (hier gezeigt für $k = 4$ Spalten)
- Ein $k$-Spalten Block propagiert einen Übertrag, wenn jede einzelne Spalte propagiert: 
  $P_{3:0} = P_3 P_2 P_1 P_0$
- Ein $k$-Spalten Block generiert einen Übertrag, wenn eine der Spalten generiert und alle Spalten darüber propagieren:
  $G_{3:0} = G_3 + P_3 G_2 + P_3 P_2 G_1 + P_3 P_2 P_1 G_0$
- Der Übertrag überspringt $k$ Spalten auf einmal: $$\begin{align} C_n & = G_{n:n-k+1} + C_{n-k} \cdot P_{n:n-k+1} \\ & = (G_n + P_n(G_{n-1} + \ldots + (P_{n-k+2} G_{n-k+1}))) + C_{n-k} \cdot \prod^n_{i=n-k+1} P_i \end{align}$$

## Block für $k$ Spalten

- Wir teilen den Addieren in $\frac{N}{k}$ Blöcke auf die jeweils $k$ Bit breit sind
- Jeder Block besteht aus
	- Einem [[Ripple-Carry-Adder (RCA)|RCA]] zum Berechnen der Summe $S_{n:n-k+1}$
	- Einer Schaltung zur schnellen Berechnung des Carries $C_n$ aus $G_{n:n-k+1}$, $P_{n:n-k+1}$ und $C_{n-k}$
	- Durch die zusätzliche Schaltung erhalten folgende Blöcke schneller ihr Carry-In

![[Pasted image 20251203185052.png]]

Das Ganze sieht dann für einen Block wie folgt aus:
![[Pasted image 20251203185154.png]]

## Kritischer Pfad

- Propagate und Generate Signale in allen Blöcken gleichzeitig berechnen
- Für große Bitbreiten $N$ dominiert $\frac{N}{K} \cdot (t_{pd, \text{AND}} + t_{pd, \text{OR}})$
- Blöcke möglichst groß wählen (kostet aber mehr Ressourcen)
- Kritischer Pfad für $N = 20$ Bit und $k = 4$:
	- RCA: $\approx 20 \cdot (t_{pd, \text{AND}} + t_{pd, \text{OR}})$
	- CLA: $\approx 10 \cdot (t_{pd, \text{AND}} + t_{pd, \text{AND}})$
		- G/P von Block 1
		- Carry zum letzten Block
		- RCA im letzten Block

![[Pasted image 20251203191146.png]]