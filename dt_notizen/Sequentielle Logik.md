---
tags:
  - foliensatz/08
  - "#MoC"
  - cleaned
aliases:
  - sequentiell
Related:
---

## Sequentielle Schaltungen

- Bei [[Kombinatorische Logik|kombinatorischer Logik]] hängen die Ausgänge nur von _aktuellen_ Eingangswerten ab
- Bei sequentiellen Schaltungen ist das anders
- Ausgänge hängen ab von 
	- Aktuellen Eingabewerten und
	- Vorherigen Eingabewerten
- Sequentielle Schaltungen speichern einen _internen_ Zustand
	- (Kurzzeit-)Gedächtnis repräsentiert bisherige Eingabesequenzen
	- Realisiert durch Rückkopplungen von Ausgängen
	- Nicht kombinatorisch

## Sequentielle Bauteile

[[Bistabile Grundschaltung]]
[[SR-Latch]]
[[JK-Latch]]
[[D-Latch]]
[[D-Flip-Flop]]
[[Flip-Flops mit Taktfreigabe]]
[[Zurücksetzbare Flip-Flops]]

## Sequentielle Logik

- Alle nicht-kombinatorischen Schaltungen
- Erlaubt Rückkopplungen, beispielsweise:

![[Pasted image 20251203195432.png]]

- Das Beispiel ist eine instabile (oszillierende) Schaltung
	- Verhalten abhängig von Herstellungsprozess, Spannung, Temperatur
	- Nicht vorhersagbar

Um das zu beheben, nutzen wir [[Synchron Sequentielle Logik]]