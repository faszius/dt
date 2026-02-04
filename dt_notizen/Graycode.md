---
tags:
  - foliensatz/06
  - cleaned
---

## Graycode

- Aufzählung von Binärzahlen einer festen Breite $k$, wobei sich (zyklisch) benachbarte Zahlen um nur ein Bit unterscheiden

![[Pasted image 20251118123430.png]]

- Konstruktion: Graycode für $k+1$ aus Graycode für $k$ mit Prefix $0$, dann umgekehrt Graycode für $k$ mit Prefix $1$

![[Pasted image 20251118123526.png]]

