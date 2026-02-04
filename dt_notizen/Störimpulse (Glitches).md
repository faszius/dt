---
tags:
  - foliensatz/06
  - cleaned
aliases:
  - Störimpuls
  - Glitch
---

## Störimpulse (Glitches)

- Eine Änderung eines Eingangs verursacht mehrere Änderungen des Ausgangs
- Können durch geeignete Entwurfsdisziplin entschärft werden
	- Ausgänge nur zu bestimmten Zeiten auswerten (synchroner Entwurf)
	- Pfade modifizieren / hinzufügen
	- Nicht alle Störimpulse können eliminiert werden (z.B. gleichzeitiges Schalten mehrerer Eingänge)
- Können durch Timing- und Karnaugh-Diagramme analysiert werden

### Beispiel für Störimpuls: Erkennen

- Was passiert, wenn $ABC$ von $011$ nach $001$ schaltet?
- $t_{pd, \text{NOT/OR}}=1, t_{pd, \text{AND}}=2$

![[Pasted image 20251121112237.png]]

![[Pasted image 20251121112246.png]]

- Wir erkennen, dass der Ausgang $Y$ kurz auf $0$ springt, obwohl sich eigentlich nichts am Wert der Gleichung ändert
- Der Glitch entsteht, wenn wir im Karnaugh-Diagramm zwischen zwei benachbarten Rechtecken springen
- Wir können die kritische Stelle im Karnaugh-Diagramm mit einem zusätzlichen Implikanten $\overline{A}C$ überdecken

![[Pasted image 20251121112458.png]]

![[Pasted image 20251121112508.png]]

