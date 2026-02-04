---
tags:
  - foliensatz/04
  - cleaned
Related:
  - "[[Maxterm]]"
aliases:
  - Konjunktive Normalform
  - KNF
---

- Produkt aller [[Maxterm|Maxterme]], für welche die Funktion _falsch_ ist
- Jede [[Boole'sche Gleichungen|boole'sche Funktion]] hat _genau eine_ KNF (abgesehen von Kommutation)
- Im Beispiel: $Y = M_0 M_3 = (A+B)(\overline{A}+\overline{B})$
- $A \oplus B$ nur kompakter Schreibweise für $(A + B)(\overline{A} + \overline{B})$

| A   | B   | Y   | Maxterm                          |
| --- | --- | --- | -------------------------------- |
| 0   | 0   | 0   | $m_0 = \overline{A}\overline{B}$ |
| 0   | 1   | 1   | $m_1 = \overline{A}B$            |
| 1   | 0   | 1   | $m_2 = A \overline{B}$           |
| 1   | 1   | 0   | $m_3 = AB$                       |
