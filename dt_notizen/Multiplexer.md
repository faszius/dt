---
tags:
  - foliensatz/05
  - cleaned
aliases:
  - MUX
---

## Multiplexer

- Selektiert einen der $n$ Dateneingänge $A_0, \ldots, A_{n-1}$ als Ausgang $Y$
- $k = \lceil \log_2 n \rceil$ Steuersignale $S_0, \ldots, S_{k-1}$
- $Y = A_{u_{2, k}(S_{k-1} \ldots S_0)}$

- Gatter: 
  ![[Screenshot 2025-11-14 at 19.49.56.png]]
- Wahrheitstabelle:
  ![[Screenshot 2025-11-14 at 19.50.37.png]]
  ![[Screenshot 2025-11-14 at 19.50.52.png]]
- Interner Aufbau:
  ![[Screenshot 2025-11-14 at 19.51.15.png]]

## Größerer Multiplexer

- Gatter:
  ![[Screenshot 2025-11-14 at 19.51.48.png]]
- Tabelle:
  ![[Screenshot 2025-11-14 at 19.52.07.png]]
- Interner Aufbau:
  ![[Screenshot 2025-11-14 at 19.52.23.png]]
