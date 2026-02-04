---
tags:
  - foliensatz/09
  - cleaned
  - "#MoC"
aliases:
  - parallel
  - Pipelines
---

## Arten der Parallelität

- Räumliche Parallelität
	- Mehrere Aufgaben durch vervielfachte Hardware gleichzeitig bearbeiten
- Zeitliche Parallelität
	- Aufgabe in mehrere Unteraufgaben aufteilen
	- Unteraufgaben parallel ausführen
- Beispiel: Fließbandprinzip bei Autofertigung ("Pipelining")
	- Nur eine Station pro Arbeitsschritt
	- Alle unterschiedlichen Arbeitsschritte für mehrere Autos parallel ausgeführt
	- Zeitliche Parallelität

## Grundlegende Begriffe

- Datensatz:
	- Vektor aus Eingabewerten, zu denen ein Vektor aus Ausgabewerten berechnet wird
- Latenz:
	- Zeit von der Eingabe eines Datensatzes bis zur Ausgabe des zugehörigen Ergebnisses
- Durchsatz:
	- Anzahl von Datensätzen, die pro Zeiteinheit bearbeitet werden können (Parallelität erhöht Durchsatz)

## Beispiel: Plätzchen backen

- Annahmen:
	- Genug Teig ist fertig
	- 5 Minuten zum Belegen eines Bleches
	- 15 Minuten Backzeit
- Sequentiell: ein Bleck nach dem anderen belegen und backen
- Zeitlich parallel: nächstes Blech belegen, während erstes noch im Ofen ist
- Räumlich parallel: zwei Bäcker:innen, jeweils mit eigenem Ofen
- Räumliche und zeitliche Parallelität kombinierbar

![[Pasted image 20251210163122.png]]

## Beispiel: Pipelining in Schaltungen

### Ohne Pipeline-Register

![[Pasted image 20251210163251.png]]
![[Pasted image 20251210163313.png]]

### Zwei Pipeline-Stufen

![[Pasted image 20251210163324.png]]
![[Pasted image 20251210163358.png]]

### Drei Pipeline-Stufen

![[Pasted image 20251210163428.png]]
![[Pasted image 20251210163436.png]]

## Bewertung Pipelining

- Pipelinestufen sollten möglichst lang sein ("ausbalanciert")
	- Längste Stufe bestimmt maximale Taktfrequenz von $f_\text{CLK}$
	- Latenz = # Pipelinestufen/Taktfrequenz
- Mehr Pipelinestufen
	- Höherer Durchsatz (mehr Ergebnisse pro Zeiteinheit), da höhere Taktfrequenz
	- Aber auch höhere Latenz (länger auf Ergebnisse warten)
	- Lohnt sich nur, wenn viele Datensätze bearbeitet werden müssen
- Probleme bei Abhängigkeiten zwischen Teilaufgaben
	- Bspw. erst Backergebnis prüfen, bevor nächstes Blech belegt wird
