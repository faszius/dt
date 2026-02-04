---
tags:
  - foliensatz/04
  - cleaned
aliases:
  - Disjunktive Normalform
  - DNF
Related:
  - "[[Minterm]]"
---

- Summe aller [[Minterm|Minterme]], für welche die Funktion _wahr_ ist
- Jede [[Boole'sche Gleichungen|boole'sche Funktion]] hat _genau eine_ DNF (abgesehen von Kommutation)
- Im Beispiel: $Y = m_1 + m_2 = \overline{A}B + A \overline{B}$

| A   | B   | Y   | Minterm                          |
| --- | --- | --- | -------------------------------- |
| 0   | 0   | 0   | $m_0 = \overline{A}\overline{B}$ |
| 0   | 1   | 1   | $m_1 = \overline{A}B$            |
| 1   | 0   | 1   | $m_2 = A \overline{B}$           |
| 1   | 1   | 0   | $m_3 = AB$                       |
