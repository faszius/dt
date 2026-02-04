---
tags:
  - foliensatz/13
  - cleaned
---

## Erklärung

Um Binärzahlen auch ein Vorzeichen zu geben, neben dem Zweierkomplement auch die "Vorzeichen und Betrag"-Darstellung benutzen.
Dabei bestimmt die höchstwertigste Ziffer das Vorzeichen der Binärzahl. Ist sie $1$, ist die Binärzahl negativ, ist die $0$, ist die Binärzahl positiv. Die restlichen Ziffern beschreiben dann den Betrag der Binärzahl.

## Definition

Formal definiert sieht das Ganze so aus:
![[Pasted image 20260201163848.png]]

## Beispiel

Als Beispiel nehmen wir die "Vorzeichen und Betrag"-Binärzahl $1010_2$. Wenn wir diese ins Dezimalsystem umrechnen wollen, rechnen wir wie folgt: $$1010 = (-1)^1 + 0 \cdot 2^2 + 1 \cdot 2^1 + 0 \cdot 2^0$$
Der einzige Unterschied zur normalen Umrechnung ist, dass wir die höchstwertigste Ziffer nur benutzen, um das Vorzeichen der Binärzahl abzulesen. Sie hat keinen Wert. Die normale $4$ lässt sich dann wie folgt beschreiben:
$$0010 = (-1)^0 + 0 \cdot 2^2 + 1 \cdot 2^1 + 0 \cdot 2^0$$
