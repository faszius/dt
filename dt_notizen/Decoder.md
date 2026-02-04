---
tags:
  - foliensatz/05
  - cleaned
---

## Decoder

- $n$ Eingänge $A_0, \ldots, A_{n-1}$
- $2^n$ Ausgänge $Y_0, \ldots, Y_{2^n-1}$
- "One-Hot" Kodierung: $Y_i = u_{2, n}(A_{n-1} \ldots A_0) == i \; ? \; 1:0$

- Gatter:
  ![[Screenshot 2025-11-14 at 19.55.41.png]]
- Tabelle:
  ![[Screenshot 2025-11-14 at 19.55.55.png]]

## Implementierung von Decodern

![[Screenshot 2025-11-14 at 19.56.29.png]]

## Logikrealisierung mit Decodern

- Summe über [[Minterm|Minterme]], auf denen Zielfunktion wahr ist
- Decoder ersetzt erste Stufe der zwistufigen Logikrealisierung

![[Screenshot 2025-11-14 at 19.57.17.png]]
![[Screenshot 2025-11-14 at 19.57.30.png]]