---
tags:
  - foliensatz/12
  - cleaned
---

![[Pasted image 20260124112934.png]]

- Für RAM in SystemVerilog benutzen wir [[SystemVerilog Arrays und Vektoren|Arrays]] und [[SystemVerilog Arrays und Vektoren|Vektoren]]
- Wir haben Inputs für:
	- Breite des Speicherfelds
	- Tiefe des Speicherfelds
	- Write Enable Signal
	- Angefragte Adresse
	- Dateninput
	- Datenoutput
- Wenn Write Enable $= 1$, dann überschreiben wir den gespeicherten Wert an der angelegten Adresse mit dem angelegten Dateninput
- Der Datenausgang entspricht immer den Daten an der angelegten Adresse