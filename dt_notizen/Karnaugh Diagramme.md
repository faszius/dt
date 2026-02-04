---
tags:
  - foliensatz/06
  - cleaned
aliases:
  - Karnaugh
  - Don't Care
  - Dont't-Care
Related:
  - "[[Graycode]]"
---

## Karnaugh Diagramme

- [[Boole'sche Gleichungen|Boole'sche Ausdrücke]] können durch Zusammenfassen von [[Minterm|Mintermen]] minimiert werden
	- $Y = AB + A \overline{B} = A$
- Karnaugh Diagramme stellen Zusammenhänge graphisch dar
	- Anordnung der Wahrheitstabelle via [[Graycode]]
	- Zusammenhängende Minterme besser erkennbar

### Beispiel

Wir wollen diese Wahrheitstabelle in ein Karnaugh-Diagramm eintragen:
![[Pasted image 20251118124102.png]]

Das sieht dann wie folgt aus:
![[Pasted image 20251118124145.png]]

Jedes Feld im Karnaugh-Diagramm entspricht einer Kombination an Eingangsvariablen - vorgegeben durch die Binärzahlen am Rand des Diagramms. Das Feld $2$ entspricht etwa der Eingangskombination $ABC = 010$, und das Feld $5$ entspricht der Eingangskombination $ABC = 101$.
Jeder Minterm beschreibt ebenso eine Kombination an Eingangsvariablen. Uns interessieren wie gewohnt nur die Minterme, für die die Tabelle auch eine $1$ ausgibt - $m_2$, $m_6$ und $m_7$. Der Minterm $m_2$ beschreibt dabei die Eingangskombination $ABC = 010$ - bedeutet, wir schreiben in das KV-Diagramm in das Feld $010$ eine $1$. Genau so gehen wir mit den anderen Mintermen vor, sodass wir am Ende drei Einsen in Diagramm haben.
Jetzt wollen wir diese Einsen nutzen, um unsere Formel zu minimieren. Dazu zeichnen wir Viereck in unser Diagramm. Jedes Viereck muss eine Zweierpotenz an Einsen umfassen - also entweder $1, 2, 4, 8, \ldots$ Einsen, und darf keine Felder beinhalten, die keine Einsen beinhalten. Vierecke dürfen sich überkreuzen. Am Ende muss jede $1$ von einem Viereck bedeckt sein.
Sobald wir so weit sind, können wir jedes Viereck mit einem Implikanten beschreiben. Das lilafarbene Viereck bedeckt die Felder $010$ und $110$, welche durch die Formel $AB$ beschrieben werden. Das blaue Viereck bedeckt die Felder $110$ und $111$, welche durch die Formel $B \overline{C}$ beschrieben werden, sodass unsere minimierte Formel am Ende durch $Y = AB + B \overline{C}$ beschrieben wird.

## Abdeckung von Mintermen durch Implikanten

- Wir haben $n$ Eingangsvariablen
- Ein Implikant aus $k \leq n$ Literalen deckt $2^{n-k}$ Minterme ab
- Ein Primimplikant ist eine nicht vergrößerbare zusammenhängende viereckige Fläche im Karnaugh Diagramm
- Primimplikanten können über den Rand hinweg gehen!

### Karnaugh Diagramm für vier Eingänge

![[Pasted image 20251120124411.png]]

![[Pasted image 20251120124416.png]]

### Karnaugh Diagramm mit "Don't Cares"

- Don't Cares sind Eingangskombinationen, die uns nicht interessieren - es ist egal, ob sie durch die minimierte Formel abgedeckt werden oder nicht
- Werden durch ein $*$ gekennzeichnet

![[Pasted image 20251120124553.png]]

![[Pasted image 20251120124558.png]]

## Minimierungsregeln für Karnaugh Diagramme

- Eintragen von Mintermen
	- Einsen aus Wahrheitstabelle
	- "Don't Cares" ($*$) für ungültige Eingangskombinationen
- Markieren von Implikanten
	- Markierte Bereiche dürfen $1$ und $*$ enthalten, aber keine $0$
	- Nur _Rechtecke_ mit $2^k$ Einträgen erlaubt (keine L- oder Z-Formen)
	- Bereiche dürfen sich überschneiden
	- Bereiche dürfen um die Ränder des Diagrammes herum reichen
	- Bereiche müssen so groß wie möglich sein (Primimplikanten)
- Ziel: Überdeckung aller Einsen mit möglichst wenigen Primimplikanten

