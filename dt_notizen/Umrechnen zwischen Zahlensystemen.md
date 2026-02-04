---
tags:
  - foliensatz/02
  - cleaned
  - foliensatz/13
Related:
---

## Binär $\rightarrow$ Dezimal

### [[Vorzeichenloses Stellenwertsystem|Vorzeichenlose Binärzahlen]]

Wenn wir eine Basis $b$ und eine Zahl $a$ in dieser Basis haben, dann lässt sich die zugehörige Dezimalzahl ausrechnen, indem wir die Ziffern von rechts nach links durchgehen. Für die Ziffer $a_i$ die wir uns gerade angucken (wobei $i$ der Index der Ziffer ist), rechnen wir $a_i \cdot b^i$ und addieren die Zahl zu unserem Ergebnis. Nachdem wir alle Ziffern durchgegangen sind, ist das Ergebnis unsere Dezimalzahl.

![[Screenshot 2025-10-17 at 10.07.54.png]]

![[Screenshot 2025-10-17 at 10.09.10.png]]

### [[Vorzeichenbehaftete Binärzahlen|Zweierkomplement]]

#### Polyadische Abbildung direkt anwenden (Methode 1)

Eine Möglichkeit ist, die Ziffern gleich von rechts nach links durchzugehen und die dazugehörigen Zweierpotenzen zu addieren, wobei die letzte Ziffer einen negativen Wert bekommt:
$$\begin{align*}
100 \; 1011_{2} = \; & -2^6 + 2^3 + 2^1 + 2^0 \\
= \; & -64 + 8 + 2 + 1 \\
= \; & -53_{10}
\end{align*}$$
#### Betrag berechnen (Methode 2)

Wenn die Binärzahl mit einer $1$ beginnt, kann man die Binärzahl durch das Komplement + 1 auch in das positive Gegenstück umwandeln, das ausrechnen und vor das Ergebnis ein Minus packen:
$$\begin{align*}
100 \; 1011_{2} = \; & -(\overline{100 \; 1011_2} + 1) \\
= & \; -(011 \; 0100_2 + 1) \\
= & \; -011 \; 0101_2 \\
= & -53_{10}
\end{align*}$$
Beginnt die Binärzahl mit einer $0$ kann man die Binärzahl einfach wie gewohnt ausrechnen:
$$000 \; 1011_2 = 11$$

### [[Vorzeichen und Betrag]]

Durch das erste Bit ist das Vorzeichen der Dezimalzahl gegeben. Ist das erste Bit eine $1$, wird die Dezimalzahl negativ, sonst positiv. Nachdem wir das Vorzeichen bestimmt haben, können wir den Rest der Binärzahl nutzen um den Betrag der Dezimalzahl auszurechnen. Danach packen wir das Vorzeichen vor die Dezimalzahl.

### [[Vorzeichenloses Stellenwertsystem mit Nachkommastellen]]

Die Ziffern vor dem Komma rechnen wir dann wie normal zusammen. Bei den Exponenten für die Ziffern nach dem Komma gehen wir anders vor - zum einen sind die Exponenten nach dem Komma alle negativ, zum anderen werden die Exponenten immer kleiner - der Exponent für die erste Ziffer nach dem Komma ist $-1$, die Exponent für die zweite Ziffer ist $-2$, usw. Als Beispiel nehmen wir die Binärzahl $110.11_2$. Wenn wir diese ins Dezimalsystem umrechnen wollen, rechnen wir wie folgt: 
$$110.11_2 = 1 \cdot 1^2 + 1 \cdot 2^1 + 0 \cdot 2^0 + 1 \cdot 2^{-1} + 1 \cdot 2^{-2} = 6.75_{10}$$

### [[IEEE 754]]

Wenn wir eine IEEE 754 Zahl ins Dezimalsystem umrechnen, haben wir den Bias und die länge des Exponenten und der Mantisse immer gegeben. Rechnen wir also folgende IEEE-754-Zahl (mit dem Bias 15) um:

![[Pasted image 20260201183230.png]]

Dazu benutzen wir die Formel $(-1)^s \cdot 1.f \cdot 2^{e - \text{bias}}$

![[Pasted image 20260201183341.png]]

$2^8$ bestimmt, dass das Komma am Ende um $8$ Stellen nach rechts geschoben werden muss.

## Dezimal $\rightarrow$ Binär

### Vorzeichenlos

Es gibt zwei verschiedene Methoden, um Dezimalzahlen in Binärzahlen umzurechnen.

#### Größtmöglichste Zweierpotenz abziehen (Methode 1)

Gegeben eine Dezimalzahl, kann man immer die höchstmögliche Zweierpotenz abziehen:
$$\begin{align*}
53_{10} = \; & 32 + \underline{21} \\
= \; & 32 + 16 + \underline{5} \\
= \; & 32 + 16 + 4 + 1 \\
= \; & 11 \; 0101_2
\end{align*}$$
Jetzt haben wir eine Folge an Zweierpotenzen, mit denen sich die Dezimalzahl beschreiben lässt - 32, 16, 4 und 1. Gehen wir die Zweierpotenzen von der kleinsten bis zur höchsten durch, können wir unsere Binärzahl von rechts nach links bauen: 
Wir haben die $1$, also setzen wir die erste Ziffer der Binärzahl auf 1. Die $2$ haben wir nicht, also setzen wir die nächste Ziffer auf 0. Die $4$ haben wir, also ist die nächste Ziffer wieder eine 1, und so weiter - bis zur höchsten Zweierpotenz, die wir ausgerechnet haben. Am Ende erhalten wir die Binärzahl $11 \; 0101_2$.

#### Halbieren mit Rest (sukzessives Durch-2-Teilen) (Methode 2)

Gegeben eine Dezimalzahl, können wir wie folgt immer durch zwei teilen:

$$\begin{align*}
53_{10} = & \; 2 \cdot \underline{26} + 1 \\
= & \; 2 \cdot (2 \cdot \underline {13} + 0) + 1 \\
= & \; 2 \cdot (2 \cdot (2 \cdot \underline{6} + 1) + 0) + 1 \\
= & \; 2 \cdot (2 \cdot (2 \cdot (2 \cdot \underline{3} + 0) + 1) + 0) + 1 \\
= & \; 2 \cdot (2 \cdot (2 \cdot (2 \cdot (2 \cdot \underline{1} + \underline{1}) + \underline{0}) + \underline{1}) + \underline{0}) + \underline{1} \\
\end{align*}$$
Indem wir immer weiter durch Zwei teilen und uns den Rest merken, der entweder $0$ oder $1$ ist, können wir mit den Resten unsere Binärzahl Stück für Stück von rechts nach links zusammenbauen. Am Ende erhalten wir mithilfe der unterstrichenen Reste die Binärzahl $11\; 0101$.

### [[Vorzeichenbehaftete Binärzahlen|Zweierkomplement]]

Es gibt auch wieder zwei verschiedene Methoden, um Dezimalzahlen in Binärzahlen umzurechnen.

#### Größtmöglichste Zweierpotenz abziehen (Methode 1)

Bei der ersten Methode ziehen wir wieder die größtmöglichste Zweierpotenz ab. Bei positiven Zahlen funktioniert das wie bei vorzeichenlosen Binärzahlen, nur das wir am Anfang noch eine $0$ hinzufügen. So wäre im Zweierkomplement $53_{10} = 011 \; 0101_2$ und nicht  $53_{10} = 11 \; 0101_2$. Um eine negative Zahl ins Zweierkomplement umzurechnen, müssen wir ein wenig anders vorgehen:
$$\begin{align*}
-53_{10} = & \; -64 + \underline{11} \\
= & \; -64 + 8 + \underline{3} \\
= & \; -64 + 8 + 2 + 1 \\
= & \; -2^6 + 2^3 + 2^1 + 2^0
= 100 \; 1011_2
\end{align*}$$
Hier finden wir zuerst die größtmögliche _negative_ Zweierpotenz, die noch kleiner als unsere Dezimalzahl ist ($-64 < -53$), und addieren den "Rest" zu dieser negativen Zweierpotenz - in diesem Fall ist $11$ unser Rest ($-64 + 11$). Dann gehen wir wie gewohnt vor und ziehen von dem Rest immer die größtmögliche Zweierpotenz ab. Am Ende gucken wir wieder, welche Zweierpotenzen wir benutzt haben und setzen für diese eine $1$, für die anderen eine $0$. Wichtig ist, dass unsere Binärzahl jetzt mit einer $1$ beginnt.

#### Komplement und inkrementieren (Methode 2)

Das ist wohl einfachste Weise, eine Dezimalzahl ins Zweierkomplement umzurechnen. Zuerst berechnen wir die Binärzahl des Betrags (also ohne dem Minus) und stellen sicher, dass vorne eine $0$ ist. Dann berechnen wir das Komplement - ersetzen jede $1$ also durch eine $0$ und jede $0$ durch eine $1$. Zuletzt addieren wir noch eine $1$ zur Zahl und erhalten die passende Binärzahl im Zweierkomplement! Ausgerechnet sieht das Ganze so aus:
$$\begin{align*}
-53_{10} = & \; \overline{53_{10}} + 1 \\
= & \; \overline{011 \; 0101_2} + 1 \\
= & \; 100 \; 1010_2 + 1 \\
= & \; 100 \; 1011_2
\end{align*}$$

### [[Vorzeichen und Betrag]]

Zuerst bestimmen wir den Betrag der Dezimalzahl. Ist die Dezimalzahl negativ, setzen wir das erste Bit der Binärzahl auf $1$, sonst $0$. Dann rechnen wir den Betrag der Dezimalzahl wie gewohnt in eine Binärzahl um und hängen die Binärzahl hinter die erste Ziffer.

### [[IEEE 754]]

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


### [[Vorzeichenloses Stellenwertsystem mit Nachkommastellen]]

Um die Vorkommastellen der Binärzahl zu bestimmen, können wir wie gewohnt vorgehen. Um die Nachkommastellen zu berechnen, machen wir hingegen folgendes. 
1. Nachkommastellen der Dezimalzahl mit $2$ multiplizieren
	- Wenn die Zahl dadurch größer gleich $1$ wird: eine $1$ zu den Nachkommastellen der Binärzahl hinzufügen und nur die Nachkommastellen des Ergebnisses behalten
	- Wenn die Zahl dadurch kleiner als $1$ bleibt, fügen wir eine $0$ zu den Nachkommastellen der Binärzahl hinzu
2. Das wird so lange wiederholt, bis:
	- Wir keine Nachkommastellen mehr haben
	- Wir die gleichen Nachkommastellen wie in einem vorigen Schritt erhalten, in dem Fall haben wir eine Periode

Betrachten wir folgendes Beispiel: wir wollen die binären Nachkommastellen zu den dezimalen Nachkommastellen $0.55$ ausrechnen. Folgendes Bild beschreibe dann die Schritte die wir machen:
![[Pasted image 20260201172852.png]]

Zum Schluss erhalten wir die binären Nachkommastellen $0.1\overline{00 \; 11}_2$, da sich die vier Schritte ab dem Schritt $0.2$ wiederholen.

## Binär $\leftrightarrow$ Hexadezimal

Um eine Binärzahl in eine Hexadezimalzahl umzurechnen, schaut man sich immer vier Bits/eine Hexadezimalziffer an. Da vier Bits, genau so wie eine Hexadezimalziffer, 16 verschiedene Zahlen beschreiben, entsprechen vier Bits (oder ein Nibble) genau einer Hexadezimalziffer. 

### Binär $\rightarrow$ Hexadezimal

Man unterteilt die Binärzahl in Nibble. Dann geht man die Nibble von rechts nach links durch und übersetzt jedes Nibble in die dazugehörige Hexadezimalziffer. 

#### Beispiel

Wir wollen die Binärzahl $11101001101000_2$ in eine Hexadezimalzahl umrechnen. Dazu unterteilen wir sie zuerst in Nibble: $(00)11 \; 1010 \; 0110 \; 1000_2$. Dann gehen wir die Nibble von rechts nach links durch und können mithilfe der Tabelle der [[Nibble-Werte]] jedem Bit seine Hexadezimalziffer zuweisen: $1000_2 = 8_{16}$, $0110_2 = 6_{16}$, $1010_2 = A_{16}$ und $0011_2 = 3_{16}$. Somit ist die umgerechnete Hexadezimalzahl $3A68_{16}$

### Hexadezimal $\rightarrow$ Binär

Man betrachtet die Hexadezimalzahl von rechts nach links Ziffer für Ziffer. Jede Ziffer übersetzt man in das dazugehörige Nibble und erhält so am Ende die passende Binärzahl. Je nachdem wie lang das Ergebnis sein soll, kann man führende Nullen hinzufügen oder weglassen.

#### Beispiel

Wir wollen die Hexadezimalzahl $3A68_{16}$ in eine Binärzahl umwandeln. Dazu gehen wir die Ziffern von rechts nach links durch und weisen jeder Ziffer mithilfe der Tabelle der [[Nibble-Werte]] jeder Ziffer ihr Nibble zu: $8_{16} = 1000_2$, $6_{16} = 0110_2$, $A_{16} = 1010_2$ und $3_{16} = 0011$. Also ist die umgerechnete Zahl $0011 \; 1010 \; 0110 \; 1000_2$.
