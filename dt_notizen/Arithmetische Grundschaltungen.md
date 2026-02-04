---
tags:
  - foliensatz/07
  - "#MoC"
  - cleaned
  - foliensatz/08
Related:
  - "[[Shifter]]"
  - "[[Addierer]]"
  - "[[Ripple-Carry-Adder (RCA)]]"
---

## Die wichtigsten arithmetischen Grundschaltungen

- [[Shifter]]
- [[Addierer]]
- [[Ripple-Carry-Adder (RCA)]]
- [[Conditional Sum Adder (CSA)]]
- [[Carry Lookahead Adder (CLA)]]

## Weitere arithmetische Grundschaltungen

### Subtrahierer

- Ein Subtrahierer kann mit [[Addierer|Addition]] und Negation realisiert werden: $A-B = A+(-B)$
- Negation im [[Vorzeichenbehaftete Binärzahlen|Zweierkomplement]]: Komplement und Inkrement
- Addierer mit NOT-Gatter an $B$-Eingängen und $C_0 = 1$

![[Pasted image 20251128140232.png]]

### Vergleich: Kleiner als

- Ein Vergleich kann mit Subtraktion realisiert werden: $A < \Leftrightarrow A-B < 0$

![[Pasted image 20251128140720.png]]

### Vergleich: Gleichheit

- Bitweise XNOR und AND-Baum

![[Pasted image 20251128140746.png]]

### Multiplizierer

- Produkt von $n$ und $m$ bit breiten Faktoren ist $n+m$ breit
- Teilprodukte aus einzelnen Ziffern des Multiplikators mit dem Multiplikanden
- Verschobene Teilprodukte danach addieren

![[Pasted image 20251128140931.png]]

Als physische Schaltung sieht das ganze so aus:
![[Pasted image 20251128140946.png]]
