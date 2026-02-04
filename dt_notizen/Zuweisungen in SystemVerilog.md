---
tags:
  - foliensatz/07
  - cleaned
  - foliensatz/09
---

## Zuweisungen in SystemVerilog

- Die Synthese beider Module ergibt den gleichen Schaltplan

### Assign Statement

![[Pasted image 20251128191623.png]]

- Auch continuous assignment genannt
- Linke Seite (LHS, "left hand side"): Variable oder Port
- Rechte Seite (RHS, "right hand side"): logischer Ausdruck
- Zuweisung, wenn der Wert von RHS sich ändert

### `always_comb`

![[Pasted image 20251128191838.png]]

- `always_comb <instruction`
	- Zuweisung ebenfalls, wenn sich der Wert von RHS ändert
	- LHS Variablen dürfen nicht von anderen Blöcken geschrieben werden

### Eigenschaften von `assign` und `always_comb`

- Werden bei Simulation immer ausgeführt, wenn sich ein Signal auf der rechten Seite ändert
- Erlauben nur kombinatorische Logik
- Reihenfolge im Quellcode oft nicht relevant
	- Nebenläufige Signalzuweisungen ("concurrent signal assignments")
	- Aber: blockierende Signalzuweisungen (`a = b`) innerhalb von Blöcken (`begin`/`end`) werden nacheinander ausgeführt

![[Pasted image 20251128192759.png]]

## Blockierende vs. nicht-blockierende Zuweisungen

- Blockierende Zuweisungen: `<signal> = <expr>;`
	- `<expr>` wird ausgewertet und an `<signal>` zugewiesen, _bevor_ nächste Zuweisung behandelt wird
	- Blockierende Zuweisungen werden in gegebener Reihenfolge (sequentiell) abgehandelt
- Nicht-blockierende Zuweisungen: `<signal> <= <expr>;`
	- `<expr>` aller nicht-blockierenden Zuweisungen in einer Sequenz werden ausgewertet, aber _noch nicht_ an `<signal>` zugewiesen, sondern nur vorgemerkt
	- nicht-blockierende Zuweisungen werden nebenläufig (parallel) abgehandelt

### Beispiel

![[Pasted image 20251210121654.png]]

### Synthese

![[Pasted image 20251210121740.png]]

## Allgemeine Regeln für synchron sequentielle Signalzuweisungen

- Interne Zustände
	- Innerhalb von `always_ff @(posedge CLK)`
	- Mit nicht-blockierenden Zuweisungen (`<=`)
	- Möglichst nur ein/wenige Zustände 
- Einfache kombinatorische Logik durch nebenläufige Zuweisungen (`assign`)
- Komplexere kombinatorische Logik
	- Innerhalb von `always_comb`
	- Mit blockierenden Zuweisungen (`=`)
- Ein Signal darf nicht
	- Von mehreren nebenläufigen Prozessen (`assign` oder `always`) beschrieben werden
	- Innerhalb eines `always` Blocks mit blockierenden und nicht-blockierenden Zuweisungen beschrieben werden

### Beispiel

![[Pasted image 20251210122409.png]]