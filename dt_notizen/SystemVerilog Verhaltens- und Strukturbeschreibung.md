---
tags:
  - foliensatz/04
  - cleaned
---

## Beispiel für Verhaltensbeschreibung

![[Screenshot 2025-11-09 at 17.37.40.png]]

- `module`
	  Beginn der Schnittstellenbeschreibung
- `example`
	  Modulname
- `input`, `output`
	  Port-Richtung
- `logic`
	  Port-Datentyp
- `a`, `b`, `c`, `y`
	  Port-Namen
- `assign`
	  (Kombinatorische) Signalzuweisung
- `~`, `&`, `|`
	  (Kombinatorische) Operatoren (NOT, AND, OR)
- `endmodule`
	  Ende der Schnittstellenbeschreibung

### Simulation von Verhaltensbeschreibungen

![[Screenshot 2025-11-09 at 17.40.41.png]]

### Synthese von Verhaltensbeschreibungen

![[Screenshot 2025-11-09 at 17.41.05.png]]

### Synthese vs. Simulation

![[Screenshot 2025-11-09 at 17.41.23.png]]

## Beispiel für Strukturbeschreibung

### Modulinstanziierung

![[Screenshot 2025-11-09 at 17.46.11.png]]

![[Screenshot 2025-11-09 at 17.46.24.png]]

![[Screenshot 2025-11-09 at 17.46.38.png]]

### Portzuweisung nach Position oder Namen

![[Screenshot 2025-11-09 at 17.47.05.png]]

![[Screenshot 2025-11-09 at 17.47.14.png]]

- Beide Module sind äquivalent!