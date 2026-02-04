---
tags:
  - foliensatz/11
  - cleaned
Related:
  - "[[Verzögerungen in SystemVerilog]]"
---

## Synthese vs. Simulation

- Synthese erstellt aus SystemVerilog Code eine Schaltung
- Simulation läuft einen Code durch, simuliert für verschiedene Eingaben das Verhalten und gibt das Ergebnis dazu aus

![[Pasted image 20260116164413.png]]

## Testbenches (Testumgebungen)

- [[Hardwarebeschreibungssprachen|HDL]]-Programm zum Testen eines anderen HDL-Moduls _vor_ der Synthese
- Getestetes Modul 
	- Unit Under Test (UUT), manchmal Device Under Test (DUT)
- Testbench kann i.d.R. nicht synthetisiert werden
	- Wird nur für Simulation benutzt
- Arten von Testbenches
	- Einfache Testbench: Testdaten werden an UUT angelegt und die Ausgaben angezeigt
	  ![[Pasted image 20260116172438.png]]
	- Selbstprüfende Testbench: die Ausgaben werden zusätzlich automatisch auf Korrektheit überprüft
	  ![[Pasted image 20260116172528.png]]

- Testbench ist Modul ohne eigene Ports (Eingänge und Ausgänge)
- Erzeugt Stimuli (Takt, Reset, Eingabedaten)
- Instanziiert "unit under test"
- Kann Ausgabedaten und Timing verifizieren
	- Erschöpfend oder zufällig
	- Grenzfälle abdecken
- Wird nicht synthetisiert
	- Nur in Testbenches ist nicht synthetisierbarer Code erlaubt
	- Es ist möglich, Verzögerungen (z.B. `#1;`) und spezielle Anweisungen wie z.B. `$display(...)` zu benutzen
	- `if-else`, `for`-Schleifen etc. können hier wie bei Softwareprogrammierung genutzt werden
	- `initial begin ... end` für Code, der ab Beginn der Simulation einmalig ausgeführt werden soll 

## Beispiel

Wir wollen folgendes Modul testen:
![[Pasted image 20260116172629.png]]

Dann könnte eine einfache Testbench so aussehen:
![[Pasted image 20260116172704.png]]

Und eine selbstprüfende Testbench so:
![[Pasted image 20260116172723.png]]

Der allgemeine Aufbau lässt sich wie folgt beschreiben:
1. Logic für UUT Ein- und Ausgänge definieren
2. UUT instanziieren
3. `initial`-Block
	1. `$dumpfile`
	2. `$dumpvars`
	3. Verschiedene Eingabekombinationen durchgehen
	4. Nach jeder Eingabe mit `#1` warten!
	5. Selbstprüfende Testbench: Ausgabe mit `if` und `$display` überprüfen
	6. `$finish`

Eine Testbench für ein anderes Modul könnte so aussehen:
![[Pasted image 20260116174653.png]]

![[Pasted image 20260116174713.png]]

## Gleichheit in Testbenches

- Achtung: zum Testen auf Gleichheit in Testbenches `===``für logische Gleichheit (vierwertig) nutzen!
- `===` testet, ob zwei Werte vierwertiger Logik logisch gleich sind
- `==` gibt z.B. immer `x` aus, sobald ein Eingang `x` ist
	- `1'bx == 1'bx` $\Rightarrow$ `x`, `1'bx == 1'bx` $\Rightarrow$ `x`
	- `1'bx === 1'bx` $\Rightarrow$ `0`, `1'bx === 1'bx` $\Rightarrow$ `1`

## Ausgabe von Statusmeldungen

- `$display(<format>, <values>*)`
- Ähnlich zu `printf` in C und Java
- Wichtige Platzhalter:
	- `%d`,`%b` und `%h` für dezimale, binäre oder hexadezimale Darstellung
	- `%t` für Zeit (mit Einheit)
- `$time` ist aktueller Zeitpunkt der Simulation
- Bspw.:
  `$display("%t: %h + %d = %b", $time, 4'b111, 4'b001, 4'b111+4'b001);`
  erzeugt: `3.o ns: f + 1 = 0000`

## Fortgeschrittenes Testen

- Erstellen effizienter Testpläne ist nicht trivial
	- Abdeckung maximieren (gezielt vs. zufällig)
	- Wiederverwendbarkeit maximieren
	- Überlappung minimieren
- Multi-Domänen Cosimulation von Hardware und
	- Software
	- Event-basierten Kommunikationsprotokollen
	- Kontinuierlichen physikalischen Prozessen
- Testgetriebene Entwicklung (test-driven development)