---
tags:
  - foliensatz/10
  - cleaned
  - "#MoC"
aliases:
  - FSM
  - Moore
  - Mealy
  - Zustandsautomat
Related:
  - "[[Hardware für endliche Zustandsautomaten]]"
  - "[[Moore vs Mealy]]"
  - "[[Zerlegen von Zustandsautomaten]]"
---

## Endliche Zustandsautomaten 

- aka Finite State Machines (FSM)
- [[Synchron Sequentielle Logik|Synchrone sequentielle]] Schaltungen mit
	- $n$ Eingabebits
	- $k$ Ausgabebits
	- _Einem_ internen Zustand (besteht aus $m \geq 1$ Bits)
	- Takt und Reset
- In jedem Takt (zur steigenden Taktflanke)
	- Reset aktiv $\rightarrow$ Zustand = Startzustand
	- Reset inaktiv $\Rightarrow$ neuen Zustand und Ausgaben aus aktuellem Zustand und Eingaben berechnen

![[Pasted image 20251219111432.png]]

## FSM Anwendungsbeispiel

- Zahlenschloss (bspw. an Tresor)
	- Eingaben: Taste i gedrückt
	- Ausgaben: Schloss öffnen, Fehlermeldung anzeigen
	- Zusammenhang zwischen ZuständenL
	  nur Öffnen, wenn letzte (4) Eingaben korrekt und in richtiger Reihenfolge
- Steuerwerk von Rechnern (Mikroarchitektur)
	- Eingaben: Bits des aktuellen Instruktionswortes
	- Ausgaben: Steuersignale für
		- Arithmetik (welche Operation)
		- Speicher (welche Operanden)
	- Zusammenhang zwischen Zuständen:
	  in Pipeline-Stufen hängen Steuersignale von anderen Instruktionen ab
- Vieles mehr (sehr häufig verwendetes Konzept)

## FSM Diagramme als gerichtete Graphen

- Zustände (States) als Knoten: z.B. $S_0, S_1, S_2, \ldots$
- Zustandsübergänge (Transitions) als Kanten
	- Als [[Boole'sche Gleichungen|boole'scher Ausdruck]] (leere Bedingung entspricht $1$, Transition sofort bei nächster steigender Taktflanke)
	- Keine zwei Kantenbedingungen gleichzeitig erfüllbar
	- Zustand bleibt unverändert, wenn keine Bedingung erfüllt
- Reset-Kante zum Startzustand
- Ausgaben
	- In Zuständen (Moore-Automat)
	- Oder an Kanten (Mealy-Automat)

Moore-Automat:
![[Pasted image 20251219112227.png]]

Mealy-Automat:
![[Pasted image 20251219112246.png]]

## FSM Beispiel für Ampelsteuerung

- Eingänge:
	- $a_k = 1 \Leftarrow$ Induktionsschleife $k$ erkennt Fahrzeug für Straße $k \in \{A, B\}$
- Ausgänge
	- $y_k \in \{\text{rot}, \text{gelb}, \text{grün}\} \Rightarrow$ Ampelphase für $k \in \{A, B\}$
- FSM für Bedarfssteuerung
	- Halte Spur grün, solange auf dieser Fahrzeuge erkannt werden
	- Ansonsten schalte aktuelle Fahrbahn über gelb nach rot und andere Fahrbahn auf grün

### Moore-Automat

![[Pasted image 20251219112502.png]]

### Mealy-Automat

![[Pasted image 20251219112524.png]]

## Zustandsübergangs- und Ausgabetabelle

- Tabellarisch darstellen, wie sich FSM pro Zustand und Eingabe verhält
- Aktueller Zustand $S$
- Nächster Zustand $S'$
- [[Karnaugh Diagramme|Don't Cares]] verwenden!
- Achtung: implizite Bedingungen (bspw. Selbstschleifen) beim Ableiten aus Diagrammen beachten

### Moore-Automat

Wir haben den folgenden Moore-Automaten gegeben: ![[Pasted image 20251219113253.png]]

Jetzt betrachten wir jeden der vier Zustände und überlegen uns, für welche Eingaben wir in welchen Zustand wechseln. Im Zustand $A$ muss $\overline{a_A}$ erfüllt sein, damit wir in $AB$ wechseln. Für alle anderen Eingaben bleiben wir in $A$. Bedeutet: in der Tabelle machen wir für $A$ zwei Einträge. 
Im ersten Eintrag beschreiben wir, dass $A$ für $a_A$ in $A$ bleibt. Da der Wert von $a_B$ dafür unwichtig ist, tragen wir für $a_A$ eine $1$ und für $a_B$ ein [[Karnaugh Diagramme|Dont't-Care]] ein. Als nächsten Zustand $S'$ tragen wir wieder $A$ ein.
Im zweiten Eintrag beschreiben wir, dass $A$ für $\overline{a_A}$ zu $AB$ wechselt. Da $a_B$ wieder egal ist, tragen wir für $a_B$ wieder ein Don't-Care ein. Als nächsten Zustand $S'$ tragen wir hier jedoch $AB$ ein.

Zustandsübergangstabelle:
![[Pasted image 20251219113225.png]]

In Moore-Automaten sind die Ausgaben von den Zuständen abhängig. Dementsprechend haben wir in der Ausgabetabelle für jeden Zustand einen Eintrag, der beschreibt, welchen Wert $y_A$ und $y_B$ in diesem Zustand haben.

Ausgabetabelle:
![[Pasted image 20251219113239.png]]

### Mealy-Automat

Mealy-Automat:
![[Pasted image 20251219113321.png]]

Für Mealy-Automaten ist die Zustandsübergangstabelle genau wie bei Moore-Automaten.

Zustandsübergangstabelle:
![[Pasted image 20251219113335.png]]

Die Ausgabetabelle bei Mealy-Automaten hängt, im Gegensatz zu Moore-Automaten, vom jetzigen Zustand _und_ der aktuellen Eingabe ab. Dementsprechend haben wir in Mealy-Automaten für jeden Ausgang von jedem Zustand einen Eintrag.
Zustand $A$ hat zum Beispiel zwei Ausgänge - einmal $a_A$ und $\overline{a_A}$. Bedeutet wir machen für $A$ zwei Einträge, einen für jeden Ausgang, und tragen für den Ausgang ein, welche Werte $y_A$ und $y_B$ an dem Übergang haben. In $A$ für $a_A$ haben wir zum Beispiel $y_A = \text{grün}$ und $y_B = \text{rot}$.

Ausgabetabelle:
![[Pasted image 20251219113350.png]]

## FSM als [[Synchron Sequentielle Logik|synchrone sequentielle]] Schaltung

- Zustands[[D-Flip-Flop|register]]
	- Speichert aktuellen Zustand $S$
	- Übernimmt nächsten Zustand $S'$ bei steigender Taktflanke
- [[Kombinatorische Logik]] realisiert
	- Zustandsübergangstabelle ("next state logic")
	- Ausgabetabelle ("output logic")
- Binäre Kodierung der Zustände und Ein-/Ausgaben notwendig

Moore:
![[Pasted image 20251219114523.png]]

Mealy:
![[Pasted image 20251219114532.png]]

## [[Zeitverhalten]] für 101 Mustererkennung

![[Pasted image 20260116160853.png]]

- Mealy-Automat erkennt Muster einen Takt früher

