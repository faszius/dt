---
tags:
  - foliensatz/12
  - cleaned
aliases:
  - FPGA
  - Field Programmable Gate Array
---

## FPGA Konfigurationsspeicher

- FPGAs verwenden feingranulare (bitweise) Konfigurationsspeicher statt wortweisen Instruktionsspeichern
- Konfigurationsspeicher realisiert mit verschiedenen Speicher-Technologien
	- Volatil (bspw. [[Static RAM (SRAM)|SRAM]]): schnell beschreibbar, benötigt aber permanente Spannungsversorgung (statische Leistungsaufnahme), oder
	- Nicht-volatil (bspw. [[Flash]]): aufwendiger Schreibzugriff, aber Zustand bleibt auch ohne Spannungsversorgung erhalten

## Aufbau

![[Pasted image 20260124125932.png]]

- P: Pin
- IOB: I/O Block
- SM: Switch Matrix
- LC: Logic Cell
- FB: Function Block

## Programmierbare Schalter

Abhängig von einem programmierten Bit C verhält sich der Schalter anders:
![[Pasted image 20260124130108.png]]

### Switch Matrix (SM)

Mit mehreren dieser programmierbaren Schalter können wir eine ganze Kreuzung programmieren:
![[Pasted image 20260124130148.png]]

## Lookup Table (LUT)

- Realisiert kombinatorische Logik
- 2 bis 6 Eingänge (im Beispiel 2: $B$, $A$)
- Häufig auch aufteilbar in kleinere LUTs
- [[Multiplexer]] (MUX)

![[Pasted image 20260124130309.png]]

## Logic Cell (LC)

- Kann als kombinatorische Logik ($Y$) und/oder Speicher ($X$) verwendet werden
- Häufig auch spezielle Carry In ($C_{in}$) für schnelle Arithmetik 

![[Pasted image 20260124130502.png]]

## Input-/Output Blocks

- $P$ wird mit physikalischen Pins verbunden
- Ausgabetreiber ($\text{OD}$) und Eingabetreiber ($\text{ID}$)
- Ausgabetreiber kann permanent oder zur Laufzeit steuerbar (durch $\text{OEN}$) aktiviert werden
- Häufig auch weitere Konfigurationsmöglichkeiten:
	- Spannungs-Level
	- Maximale Stromstärke

![[Pasted image 20260124130713.png]]

## Funktionsblöcke

- Häufig verwendete Logikbausteine als begrenzte Ressourcen verfügbar