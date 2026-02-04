---
tags:
  - foliensatz/13
  - cleaned
---

## IEEE 754 Zahlendarstellung

In der IEEE 754 Zahlendarstellung haben wir 32 Bits, die wie folgt unterteilt sind:

![[Pasted image 20260201174258.png]]

Damit können wir Zahlen im Format $a \cdot b^c$ speichern, zum Beispiel $2.7424 \cdot 10^2$. Im Binärsystem ausgedrückt also Zahlen im Format $(-1)^s \cdot 1.f \cdot 2^{e - \text{bias}}$. Wir haben
- 1 Bit $s$ für das Vorzeichen
	- Speichert ob die Zahl positiv oder negativ ist
- 8 Bits $e$ für den Exponenten
	- Speichert um wie viele Bits das Komma in der Mantisse nach vorne oder hinten verschoben wird
- 23 Bits für die Mantisse
	- Speichert die eigentliche Zahl
- Einen Bias, mithilfe dessen wir negative Exponenten darstellen können (der Exponent selbst ist nämlich vorzeichenlos)

## Umrechnung IEEE 754 $\Rightarrow$ Dezimal

Wenn wir eine IEEE 754 Zahl ins Dezimalsystem umrechnen, haben wir den Bias und die länge des Exponenten und der Mantisse immer gegeben. Rechnen wir also folgende IEEE-754-Zahl (mit dem Bias 15) um:

![[Pasted image 20260201183230.png]]

Dazu benutzen wir die Formel $(-1)^s \cdot 1.f \cdot 2^{e - \text{bias}}$

![[Pasted image 20260201183341.png]]

$2^8$ bestimmt, dass das Komma am Ende um $8$ Stellen nach rechts geschoben werden muss.

## Dezimalzahl $\Rightarrow$ IEEE 754

Wollen wir eine Dezimalzahl (bspw. $34.25$) im Dezimalsystem in IEEE 754 (5 Bit Exponent, 10 Bit Mantisse, Bias = 15) umrechnen, gehen wir wie folgt vor:
1. Vorzeichen bestimmen und eintragen
	- Dezimalzahl ist positiv, das erste Bit der IEEE-754-Zahl ist also $0$
2. Dezimalzahl in Binärzahl umrechnen:
	- $34.25_10 = 100010.01_2$
3. Binärzahl verschieben, sodass die erste $1$ direkt vor dem Komma steht:
	- $100010.01_2 = 1.0001001 \cdot 2^5$
4. Exponenten bestimmen
	- Wir wissen dass der Bias = 15 ist, den Exponenten bestimmen wir also wie folgt:
	  $e-15 = 5 \Rightarrow e = 20$
5. Exponenten und Mantisse eintragen
	- Jetzt wo wir den Exponenten wissen, können wir die nächsten 5 Bits der Zahl eintragen, und mit der Mantisse (die Bits nach dem Komma) gleich die nächsten 10 Bits

## Weitere Merkmale

Der IEEE 754 Standard enthält sehr viele verschiedene bestimmte Kombinationen für bestimmte Zahlen (NaN, $+\infty$, $-\infty$), allgemein können wir mit einer gegebenen Anzahl Bits in IEEE 754 also weniger Zahlen darstellen als mit den anderen Darstellungen
