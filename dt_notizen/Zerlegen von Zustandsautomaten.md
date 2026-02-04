---
tags:
  - foliensatz/11
  - cleaned
---

## Zerlegen von [[Endliche Zustandsautomaten|Zustandsautomaten]]

- Aufteilen komplexer FSMs in einfachere interagierende FSMs
- Beispiel: Ampelsteuerung mit Modus für Festumzüge (Ampel B bleibt permanent grün)
	- FSM bekommt zwei weitere Eingänge: $a_F, a_R$
	- $a_F = 1 \Rightarrow$ aktiviert Festumzugsmodus
	- $a_R = 1 \Rightarrow$ deaktiviert Festumzugsmodus

## Unzerlegte FSM

![[Pasted image 20260116161332.png]]

## Zerlegung in kommunizierende FSMs

Aufbau:
![[Pasted image 20260116161401.png]]

Modus FSM:
![[Pasted image 20260116161425.png]]

Ampel FSM:
![[Pasted image 20260116161437.png]]