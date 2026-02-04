---
tags:
  - foliensatz/13
  - cleaned
---

## Erklärung

Jetzt wollen wir vorzeichenlosen Zahlen auch Nachkommastellen geben. Dazu können wir in einer Zahl einfach ein Komma setzen. Die Ziffern vor dem Komma rechnen wir dann wie normal zusammen. Bei den Exponenten für die Ziffern nach dem Komma gehen wir anders vor - zum einen sind die Exponenten nach dem Komma alle negativ, zum anderen werden die Exponenten immer kleiner - der Exponent für die erste Ziffer nach dem Komma ist $-1$, der Exponent für die zweite Ziffer ist $-2$, usw.

## Definition

Formal definiert sieht das Ganze so aus:
![[Pasted image 20260201171135.png]]

## Beispiel

Als Beispiel nehmen wir die Binärzahl $110.11_2$. Wenn wir diese ins Dezimalsystem umrechnen wollen, rechnen wir wie folgt: $$110.11_2 = 1 \cdot 1^2 + 1 \cdot 2^1 + 0 \cdot 2^0 + 1 \cdot 2^{-1} + 1 \cdot 2^{-2} = 6.75_{10}$$
