---
tags:
  - foliensatz/02
  - cleaned
---

## Erklärung

- Notwendig, um unterschiedlich breite [[Teile von Bitfolgen|Bitfolgen]] zu [[Addition von Binärzahlen|addieren]].
- Zero extension:
	- Auffüllen mit führenden Nullen für eine [[Vorzeichenloses Stellenwertsystem|vorzeichenlose Darstellung]]
		![[Screenshot From 2025-10-22 18-50-48.png]]
- Sign extension:
	- Auffüllen mit Wert des Vorzeichen-Bits für [[Vorzeichenbehaftete Binärzahlen|Zweierkomplement]]-Darstellung
		![[Screenshot From 2025-10-22 18-52-01.png]]

## Beispiel

Als Beispiel erweitern wir $-5_{10}$ im Zweierkomplement von 4 auf 8 Bit:
$$\begin{align*}
5_{10} = & \; 0101_2 \\
\Rightarrow -5_{10} = & \; \overline{0101_2} + 1 \\
= & \; 10101_2 + 1 \\
= & \; 1011_2 \\
= & \; \underline{1111} \; 1011_2
\end{align*}$$
Wobei die unterstrichenen Einsen die Bitbreitenerweiterung darstellen.