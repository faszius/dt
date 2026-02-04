---
tags:
  - foliensatz/05
  - cleaned
Related:
  - "[[Bubble Pushing]]"
  - "[[Mehrwertige Logik]]"
---

## Boole'sche Algebra

- Rechenregeln [[Boole'sche Gleichungen|boole'scher Gleichungen]]
	- Axiome: grundlegende Annahmen der Algebra (nicht beweisbar)
	- Theoreme: komplexere Regeln, die sich aus Axiomen ergeben (beweisbar)
- Analog zur Algebra auf natürlichen Zahlen
- Ergänzt um Optimierungen durch Begrenzung auf $\mathbb{B}$
- Axiome und Theoreme haben jeweils duale Entsprechung: AND $\leftrightarrow$ OR, 0 $\leftrightarrow$ 1

## Axiome der boole'schen Algebra

- Dualität: AND $\leftrightarrow$ OR, 0 $\leftrightarrow$ 1

![[Screenshot 2025-11-13 at 16.22.25.png]]

## Theoreme der boole'schen Algebra

![[Screenshot 2025-11-13 at 16.22.49.png]]

### Liste der Theoreme

#### T1: Neutralität von $1$ und $0$

![[Screenshot 2025-11-13 at 16.23.12.png]]

#### T2: Extremum von $0$ und $1$

![[Screenshot 2025-11-13 at 16.23.34.png]]

#### T3: Idempotenz

![[Screenshot 2025-11-13 at 16.23.50.png]]

#### T4: Involution

![[Screenshot 2025-11-13 at 16.24.07.png]]

#### T5: Komplement

![[Screenshot 2025-11-13 at 16.24.22.png]]

#### T6: Kommutativität

![[Screenshot 2025-11-13 at 16.24.39.png]]

#### T7: Assoziativität

![[Screenshot 2025-11-13 at 16.24.59.png]]

#### T8: Distributivität

![[Screenshot 2025-11-13 at 16.25.56.png]]

#### T9: Absorption

![[Screenshot 2025-11-13 at 16.27.18.png]]

#### T10: Zusammenfassen

![[Screenshot 2025-11-13 at 16.27.32.png]]

#### T11: Konsensus

![[Screenshot 2025-11-13 at 16.28.50.png]]

#### T12: De Morgan

![[Screenshot 2025-11-13 at 16.29.03.png]]

##### De Morgan'sche Regeln

- Das Komplement des Produkts ist die Summe der Komplemente
- Das Komplement der Summe ist das Produkt der Komplemente

### Beweis für Theoreme

- Methode 1: Überprüfen aller Möglichkeiten
- Methode 2: Gleichung durch Axiome und andere Theoreme vereinfachen

#### Überprüfen aller Möglichkeiten

##### Beweis für Distributivität (T8)

- Durch Überprüfen aller Möglichkeiten

![[Screenshot 2025-11-13 at 16.32.44.png]]

#### Anwendung von Axiomen und Theoremen

##### Beweis für Absorption (T0)

- Durch Anwendung von Axiomen und Theoremen

![[Screenshot 2025-11-13 at 16.33.07.png]]

##### Beweis für Zusammenfassen  (T10)

- Durch Anwendung von Axiomen und Theoremen

![[Screenshot 2025-11-14 at 18.41.57.png]]

##### Beweis für Konsensus (T11)

- Durch Anwendung von Axiomen und Theoremen

![[Screenshot 2025-11-14 at 18.42.48.png]]

### Logikminimierung

- Gatter-Realisierung per DNF kann sehr aufwändig sein
- Um das zu vermeiden wollen wir die Logik (Anzahl Literale und Operatoren) minimieren

#### Beispiel

![[Screenshot 2025-11-14 at 18.45.29.png]]

- Sind weitere Vereinfachungen möglich?
- Der minimale Ausdruck wäre $Y = \overline{B} + AC$
- Systematik notwendig, um minimale Ausdrücke zu erkennen/finden

