---
tags:
  - foliensatz/05
  - cleaned
---

## Bubble Pushing

- Verwendet die De Morgan'schen Gesetze und Involution
- Mit Bubble Pushing lassen sich Schaltungen Graphisch umformen

![[Screenshot 2025-11-14 at 19.12.19.png]]

## Invertierungsblasen verschieben

- Über Gatter (AND/OR/NOT/BUF) hinweg
	- Vorwärts: 
		  Eingang $\rightarrow$ Ausgang
	- Rückwärts: 
		  Ausgang $\rightarrow$ Eingang
	- Art des Gatters ändern
		  AND $\leftrightarrow$ OR
	- Blasen an allen Eingängen ändern:
		  vorhanden $\leftrightarrow$ nicht vorhanden
	- Blase an Ausgang ändern:
		  vorhanden $\leftrightarrow$ nicht vorhanden
- Zwischen Gattern
	- Vorwärts:
		  Treiber $\rightarrow$ alle Empfänger
	- Rückwärts:
		  Alle Empfänger $\rightarrow$ Treiber
	- Doppelte Blasen heben sich gegenseitig auf (Involution)
- Verbleibende Buffer (vorher Inverter) können entfernt werden

## Beispiel

![[Screenshot 2025-11-14 at 19.24.39.png]]

## Anwendungen

- Schaltungen vereinfachen
	- Weniger Inverter
	- Weniger Literale (z.B. nur $A$ statt $A, \overline{A}$)
	- Weniger verschiedene Gatter-Arten
		- Einfache Zellbibliothek (z.B. nur AND, kein OR)
- Komplementäre Schaltungen für CMOS-Schaltung ableiten
	- $Y$ für Pull-Up Netzwerk $\leftrightarrow$ $\overline{Y}$ für Pull-Down Netzwerk
	- $Y = \overline{A}B + C$
	- $\overline{Y} = \overline{\overline{A}B + C} = \overline{\overline{A}B} \overline{C} = (A+\overline{B})\overline{C}$ 