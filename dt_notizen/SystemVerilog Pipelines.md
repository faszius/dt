---
tags:
  - cleaned
---
Pipelines in Systemverilog in der Vorlesung nie offiziell vorgestellt, aber es gibt eine Übungsaufgabe zu ihnen (Übung 9.4). In der Lösung der Übung sind Pipelines wie folgt aufgebaut:

![[Screenshot 2026-02-04 at 18.23.28.png]]
![[Screenshot 2026-02-04 at 18.23.39.png]]

1. Ein [[D-Flip-Flop|Flip-Flop]] um abhängig von SET den Eingang des ersten Registers zu setzen
2. Ein [[Flip-Flop]] um den Ausgang einer Stufe in die nächste Stufe zu bewegen
3. Instanziierung der Pipeline-Stufen
4. Definition des Outputs
5. Definition der einzelnen Pipeline-Module