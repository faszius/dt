---
tags:
  - foliensatz/07
  - cleaned
---

## Verknüpfungsoperatoren

- Wir unterscheiden zwischen bitweisen/logischen Verknüpfungsoperatoren und Reduktionsoperatoren

### Logische Verknüpfungsoperatoren

- Bitweise Verknüpfungsoperatoren verknüpfen die einzelnen Ziffern mehrerer [[SystemVerilog Arrays und Vektoren|Vektoren]] miteinander
- Logische Operatoren verknüpfen ganze Vektoren miteinander

![[Pasted image 20251128190256.png]]

### Reduktionsoperatoren 

- Reduktionsoperatoren hingegen machen aus einem langen Vektor einen Wahrheitswert, indem sie den Operator mit den Elementen des Vektors anwenden

![[Pasted image 20251128190400.png]]

Analog mit
- `|` OR
- `^` XOR
- `~|` NOR
- `~&` NAND
- `~^` XNOR
