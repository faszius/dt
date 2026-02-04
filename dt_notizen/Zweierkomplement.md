---
tags:
  - foliensatz/02
  - cleaned
---

## Erklärung

Um Binärzahlen auch ein Vorzeichen zu geben, können wir das Zweierkomplement benutzen.
Dabei behandeln wir Binärzahlen erst mal wie [[Vorzeichenloses Stellenwertsystem|vorzeichenlose Binärzahlen]], nur dass die höchstwertigste Ziffer (also die ganz rechts) jetzt keinen positiven Wert mehr beschreibt, sondern einen negativen.

## Definition

Formal definiert sieht das Ganze so aus:
![[Screenshot From 2025-10-21 19-53-31.png]]

## Beispiel

Als Beispiel nehmen wir die Binärzahl $1010_2$. Wenn wir diese ins Dezimalsystem umrechnen wollen, rechnen wir wie folgt: $$1010 = 0 \cdot 2^0 + 1 \cdot 2^1 + 0 \cdot 2^2 + 1 \cdot (-2^3) = -6_{10}$$ Der einzige Unterschied zur normalen Umrechnung ist, dass die höchstwertigste Ziffer jetzt nicht mit $2^3$, sondern mit $-(2^3)$ multipliziert wird.
Die normale $6$ lässt sich dann wie folgt beschreiben: $$0110_2 = 0 \cdot 2^0 + 1 \cdot 2^1 + 1 \cdot 2^2 + 0 \cdot (-2^3)$$ Wichtig ist auf jeden Fall, dass die Zahl eine $0$ vorne stehen hat!

## Addition im Zweierkomplement

Wenn wir zwei Binärzahlen im Zweierkomplement miteinander addieren wollen, können wir wie bei der normalen [[Addition von Binärzahlen]] vorgehen und jegliche Überläufe ignorieren:

![[Screenshot From 2025-10-21 20-12-13.png]]

