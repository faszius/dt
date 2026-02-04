---
tags:
  - foliensatz/10
  - cleaned
Related:
  - "[[Endliche Zustandsautomaten]]"
---

## Rezept: [[Endliche Zustandsautomaten|FSM]] in Hardware übersetzen

- Ziel: Realisieren von FSM in Hardware / Synthese von SystemVerilog Code
- Vorgehen: Problem $\rightarrow$ FSM $\rightarrow$ Zustandsübergangs- und Ausgabetabelle $\rightarrow$ Gleichung $\rightarrow$ Schaltung
	1. Problem: Problembeschreibung, z.B. Mustererkennung für 101, z.B. textuell
	2. FSM: Wähle zwischen Moore oder Mealy Automat
	3. Zustände kodieren, Zustandsübergangs- und Ausgabetabelle, [[Karnaugh Diagramme|Don't Cares]]
	4. Gleichungen aus beiden Tabellen ableiten + minimieren
	5. Schaltungen für next State logic und output logic aus minimierten Gleichungen ableiten, mit [[D-Flip-Flop|Registern]] zu FSM zusammensetzen

## Moore Automat für 101 Mustererkennung

Wir schauen uns den folgenden Moore-Automaten für 101 Mustererkennung an:

Zustandskodierung:
![[Pasted image 20251220153013.png]]

Zustandsübergangstabelle:
![[Pasted image 20251220153027.png]]

Ausgabetabelle:
![[Pasted image 20251220153036.png]]

Zeichnung:
![[Pasted image 20251220153049.png]]

### Logikgenerierung und -minimierung

Um die Logik zu minimieren, schauen wir uns die Bits an, die in der Tabelle den _nächsten_ Zustand kodieren, also $s_1'$ und $s_0'$. Diese tragen wir in zwei Karnaugh-Diagramme ein, welche von dem _jetzigen_ Zustand $s1 s0$ und den Eingängen (in diesem Fall nur $a$) abhängen. Bedeutet wir haben zwei Tabellen, die uns sagen, für welche Bits $s_1 s_0$ und $a$ wir welche Bits $s_1' s_0'$ erhalten.
Dann erstellen wir noch ein Diagramm für $y$ abhängig von $s_1 s_0$.

Diese Diagramme können wir dann ganz einfach zum Minimieren benutzen und erhalten Formeln für $s_1'$, $s_0'$ und $y$:
![[Pasted image 20251220190707.png]]

### Schaltwerk

Aus den Formeln ergibt sich dann folgende Schaltung:
![[Pasted image 20251220190743.png]]

## Mealy Automat für 101 Mustererkennung

Wir schauen uns den folgenden Moore-Automaten für 101 Mustererkennung an:

Zustandskodierung:
![[Pasted image 20251220191055.png]]

Zustandsübergangstabelle:
![[Pasted image 20251220191108.png]]

Ausgabetabelle:
![[Pasted image 20251220191119.png]]

Zeichnung:
![[Pasted image 20251220191138.png]]

## Logikgenerierung und -minimierung mit [[Karnaugh Diagramme|Don't Cares]]

An sich funktioniert die Logikgenerierung bei Mealy-Automaten wie bei Moore-Automaten. Der einzige Unterschied ist, dass wir bei dem Karnaugh-Diagramm für die Ausgabe auch noch die Eingänge haben, da beim Mealy-Automaten die Ausgaben von dem Zustand _und_ den Eingängen abhängen.

Hier haben wir jedoch auch noch den Fall, dass wir zwar genug Bits benutzen, um vier Zustände zu kodieren, jedoch nur drei benutzen. In diesem Fall setzen wir überall da, wo wir den vierten Zustand (in diesem Fall $s_1 s_0 = 11$) beschreiben, Don't Cares hin:
![[Pasted image 20251220191441.png]]

### Schaltwerk

![[Pasted image 20251220191529.png]]

