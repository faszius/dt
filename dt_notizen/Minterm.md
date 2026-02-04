---
tags:
  - foliensatz/04
  - cleaned
Related:
aliases:
  - Minterme
---
- Produkt (Implikant), das _jede_ Eingangsvariable _genau einmal_ enthält
- Entspricht einer Zeile in einer Wahrheitswertetabelle
- Jeder Minterm wird für _genau_ eine Eingangskombination wahr 
  (unabhängig von Ergebnisspalte)
- Beispiel:

| A   | B   | Y   | Minterm                          |
| --- | --- | --- | -------------------------------- |
| 0   | 0   | 0   | $m_0 = \overline{A}\overline{B}$ |
| 0   | 1   | 1   | $m_1 = \overline{A}B$            |
| 1   | 0   | 1   | $m_2 = A \overline{B}$           |
| 1   | 1   | 0   | $m_3 = AB$                       |
