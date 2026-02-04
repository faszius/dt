---
tags:
  - foliensatz/09
  - cleaned
---

## [[D-Latch]]

![[Pasted image 20251210120731.png]]

- `always @* if (CLK) Q <= D;`
	- Sobald sich `D` ändert, wird `if (CLK) Q <= D;` ausgewertet und gegebenenfalls `Q` neu zugewiesen
- `always_latch if (CLK) Q <= D;` ist eine Kurzschreibweise von genau dem gleichen

## [[D-Flip-Flop]]

![[Pasted image 20251210120924.png]]

## Weitere Beispiele

### [[Zurücksetzbare Flip-Flops]]

![[Pasted image 20251210121004.png]]

### Schaltung mit D-FLip-Flops

![[Pasted image 20251210121053.png]]