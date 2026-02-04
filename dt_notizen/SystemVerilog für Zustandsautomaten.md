---
tags:
  - foliensatz/10
  - cleaned
Related:
  - "[[Endliche Zustandsautomaten]]"
---

## Beispiel Mustererkennung

- Typisch in Bild- und Textanalyse (bspw. Suche nach regulären Ausdrücken)
- Bspw.: erkenne  [[Teile von Bitfolgen|Bitfolge]] "101" in Bitsequenz
	- Auch überlappend, "10101" enthält z.B. zweimal "101"
- Eingänge: das nächste Bit $a \in \mathbb{B}$
- Ausgabe: $y = 1 \Rightarrow$ gewünschte Bitfolge erkannt

### Umsetzung

![[Pasted image 20251220150034.png]]

## Grundidee für [[Endliche Zustandsautomaten|FSM]]-Modellierung in Systemverilog

Vorgehen:
- `logic`-[[SystemVerilog Arrays und Vektoren|Vektor]] nutzen, um Zustände zu kodieren
	- Mittels Zustandskodierung $\text{cs}: S \rightarrow \mathbb{B}^m$
	- Jedem Zustand einen $m$ Bit breiten Wert zuordnen, z.B. als $\text{cs}(S_k) = (s_{m-1} \ldots s_0)$ mit $\text{u}_{2, m}(s_{m-1} \ldots s_0) = k$
	- Für 101 Mustererkennung: $\text{cs}(S_0) = 00_2, \text{cs}(S_0) = 00_2 \text{cs}(S_1) = 01_2, \text{cs}(S_2) = 10_2, \text{cs}(S_3) = 11_2$
	- Kodierung der Ein-/Ausgänge ist i.d.R. von der Anwendung vorgegeben
- Rücksetzbare [[D-Flip-Flop|Flip-Flops]] als Zustandsspeicher
- [[Kombinatorische Logik|Kombinatorische]] next-state Logik durch `case` in `always_comb` Block
- Kombinatorische Ausgabe-Logik durch nebenläufige Zuweisungen

## Moore-Automat für 101 Mustererkennung

![[Pasted image 20251220150643.png]]

SV-Automaten sind immer gleich aufgebaut

1. `logic` für `state` und `nextstate` (Größe abhängig von der Anzahl der Zustände)
2. `always_ff` für `RST` und `next_state` (wirklich fast immer gleich)
3. `always_comb` für next_state Logik
	- Abhängig vom Zustand
	- Für jeden Zustand gehen wir mit dem ternären Operator alle möglichen Übergangsbedingungen durch und definieren den nächsten Zustand
	- Beispiel:
	  `2'd0: nextstate = A ? 2'd1 : 2'd0`
	  Wenn wir im Zustand `2'd0` ($00$) sind, schauen wir uns `A` an. Wenn `A` wahr ist, wechseln wir in `2'd1` ($01$), sind bleiben wir in `2'd0` ($00$)
4. `assign Y` für output Logik 
	- Hängt bei Moore-Automaten vom Zustand ab
	- Hängt bei Mealy-Automaten vom Zustand und Eingang ab

## Mealy-Automat für 101 Mustererkennung

![[Pasted image 20251220150625.png]]

Der einzige Unterschied vom Aufbau her ist, dass unser `Y` vom Zustand _und_ der Eingabe abhängt

## Timing-Diagramm

![[Pasted image 20251220151814.png]]