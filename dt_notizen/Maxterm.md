---
tags:
  - foliensatz/04
  - cleaned
Related:
  - "[[Konjunktive Normalform (KNF)]]"
aliases:
  - Maxterme
---

- Summe, welche _jede_ Eingangsvariable _genau einmal_ enthält
- Entspricht einer Zeile in Wahrheitstabelle
- Entspricht einer Zeile in Wahrheitswertetabelle
- Jeder Maxterm wird für _genau eine_ Eingangskombination _falsch_
  (Unabhängig von Ergebnisspalte)

| A   | B   | Y   | Maxterm                  |
| --- | --- | --- | ------------------------ |
| 0   | 0   | 0   | $M_0 = A+B$              |
| 0   | 1   | 1   | $M_1 = A + \overline{B}$ |
| 1   | 0   | 1   | $M_2 = \overline{A} + B$ |
| 1   | 1   | 0   | $M_3 = \overline{A} + B$ |
