---
tags:
  - foliensatz/08
  - foliensatz/09
  - cleaned
aliases:
  - synchron sequentiell
  - synchrone sequentielle
Related:
  - "[[Sequentielle Logik]]"
---

## Entwurf synchroner [[Sequentielle Logik|sequentieller Logik]]

- Rückkopplungen durch [[D-Flip-Flop|Register]] aufbrechen
	- Halten den Zustand der Schaltung
	- Ändern Zustand nur zur Taktflanke
	- Gesamte Schaltung synchronisiert mit Taktflanke

![[Pasted image 20251203195807.png]]

## Synchrone sequentielle Schaltungen

- Regeln für Aufbau synchron sequentieller Schaltungen
	- Jedes Schaltungselement ist entweder Register oder [[Kombinatorische Logik|kombinatorische Schaltung]]
	- Mindestens ein Schaltungselement ist ein Register
	- Alle Register werden durch das gleiche Taktsignal gesteuert
	- Jeder zyklische Pfad enthält mindestens ein Register
- Anwendungsbeispiele
	- [[Parallelität|Pipelines]]
	- [[dt_notizen/Endliche Zustandsautomaten]]

## [[Zeitverhalten]] synchron sequentieller Logik

### Zeitverhalten eines Registers (Flip-Flop)

- Flip-Flop übernimmt $D$ zur steigenden Taktflanke
- Was passiert bei zeitgleicher Änderung von $D$ und $\text{CLK}$?
- Bisher vereinfachte Annahme:
	- Wert unmittelbar vor der Taktflanke wird übernommen
- Aber:
	- Was heißt "unmittelbar"?
	- Wie schnell wird der neue Zustand am Ausgang sichtbar?
	- Was muss daher bei synchronen sequentiellen Schaltungen beachtet werden?

![[Pasted image 20251210153407.png]]

### Zeitanforderungen an DFF Eingangssignal

- Dateneingang $D$ muss im Abtast-Zeitfenster um Taktflanke stabil sein, um [[Metastabilität]] zu vermeiden
- $t_\text{setup}$
	- Zeitintervall vor Taktflanke, in dem $D$ stabil sein muss ("setup time")
- $t_\text{hold}$
	- Zeitintervall nach Taktflanke, in dem $D$ stabil sein muss ("hold time")
- $t_\text{a}$
	- Abtastfenster: $t_\text{a} = t_\text{setup} + t_\text{hold}$ ("aperture time")
- Größenordnung: 10ps

![[Pasted image 20251210160156.png]]

### Zeitcharakteristik des DFF Ausgangssignals

- Verzögerung des Registerausgangs relativ zur steigenden Taktflanke
	- Kontaminationsverzögerung ($t_\text{ccq}$): kürzeste Zeit bis $Q$ umschaltet
	  ("contamination delay clock-to-Q")
	- Laufzeitverzögerung ($t_\text{pcq}$): längste Zeit bis $Q$ sich stabilisiert
	  ("propagation delay clock-to-Q")
- Größenordnung: 10ps

![[Pasted image 20251210160657.png]]

### Dynamische Entwurfsdisziplin

- [[Kombinatorische Logik]] zwischen zwei Registern hat min. Verzögerung $t_\text{cd}$ und max. Verzögerung $t_\text{pd}$
- $D_2$ abhängig von Verzögerungen der Gatter und des _ersten_ Registers
- Timing-Bedingungen des zweiten Registers müssen erfüllt werden
	- $t_{\text{ccq}, 1} + t_\text{cd} \geq t_{\text{hold}, 2}$
	- $t_{\text{pcq}, 1} + t_\text{pd} + t_{\text{setup}, 2} \leq t_{\text{CLK}, 2}$
- Maximale Taktrate wird durch _kritischen_ Pfad bestimmt
	- $f_\text{CLK} = \frac{1}{t_\text{CLK}} \leq \frac{1}{t_\text{pcq} + t_\text{pd} + t_\text{setup}}$

![[Pasted image 20251210161744.png]]

#### Beispiel

Analyse der Timing-Bedingungen:
![[Pasted image 20251210161811.png]]

Beheben der verletzten Hold-Zeitanforderung:
![[Pasted image 20251210161849.png]]

### Asynchrone Eingänge

- Wie geht man mit asynchrone Eingängen um?
	- Z.B. Eingaben
	- Kommunikationssignale von externen ICs
- Timing-Bedingungen können nicht garantiert werden
- Schiebe[[D-Flip-Flop|register]] für Synchronisation
	- Erstes Flip-Flop kann [[Metastabilität|metastabil]] werden
	- Kippt i.d.R. vor nächster Taktflanke in stabilen Zustand
	- Zweites Flip-Flop wird nicht metastabil

![[Pasted image 20251210162200.png]]
![[Pasted image 20251210162212.png]]

