---
tags:
  - foliensatz/08
  - cleaned
---

## Zurücksetzbare Flip-Flops

- Reset setzt internen Zustand unabhängig von $D$ auf $0$
	- Synchron: nur zur steigenden Taktflanke wirksam
	- Asynchron: jederzeit (unabhängig von CLK)
- Anwendungsbeispiele:
	- Sequentielle Schaltung in definierten Ausgangszustand versetzen
- Setzbare Flip-Flops analog

Darstellung des Gatters:
![[Pasted image 20251203195201.png]]

Aufbau des Gatters:
![[Pasted image 20251203195223.png]]

## Anwendungsbeispiel: (Shift-)Register

- Register bestehend aus parallelen D-Flip-Flops
- Bei Shift-Register ist $D_i = Q_{i-1}$

![[Pasted image 20251203195313.png]]