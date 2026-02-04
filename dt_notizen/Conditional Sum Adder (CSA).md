---
tags:
  - foliensatz/08
  - cleaned
aliases:
  - CSA
---

## Conditional Sum Adder

![[Pasted image 20251203182231.png]]

- Wir betrachten einen in zwei geteilten [[Ripple-Carry-Adder (RCA)|RCA]]
- Der Übertrag vom unteren ins obere Halbwort kann nur $0$ oder $1$ sein
- Für beide Optionen kann das obere Halbwort schonmal vorberechnet werden
- Dann kann das richtige Ergebnis ausgewählt werden, sobald der tatsächliche Übertrag bekannt ist
- Nach dem halben CSA folgt nur noch ein [[Multiplexer|MUX]] auf dem kritischen Pfad

