---
tags:
  - MoC
  - linker-exclude
---

[[Beherrschen von Komplexität]]
	[[Abstraktion]]
	[[Disziplin]]
	[[Hierarchie, Modularität und Regularität]]
		>Verständnis für die Begriffe aus der Vorlesung haben
***
[[Hardwarebeschreibungssprachen]]
[[SystemVerilog]]
	[[SystemVerilog für numerische Literale]]
		>Numerische Literale in SystemVerilog darstellen können
	[[SystemVerilog Syntax]]
	[[SystemVerilog Module]]
		[[SystemVerilog Verhaltens- und Strukturbeschreibung]]
			>Aufbau eines Moduls können, Module selbst schreiben können
			>Submodule instanziieren und verwenden können 
			>Einfache Module ohne Probleme selbst schreiben (z.B. Eingänge A und B, Ausgang Y, berechnet irgendeine Formel mit A und B)
	[[SystemVerilog Datentypen]]
		[[SystemVerilog Arrays und Vektoren]]
			>Verschiedene Datentypen kennen und verwenden können
			>Vor allem Vektoren verstehen! (auch Unterschied zu Arrays)
			>Wichtig bei Vektoren: Operationen auf Vektoren und **Unterschied bitweise/logische/unäre Operationen!**
	[[SystemVerilog für kombinatorische Logik]]
		[[SystemVerilog für Logikgatter]]
		[[SystemVerilog Verknüpfungsoperatoren]]
		[[Zuweisungen in SystemVerilog]]
			>Funktionsweise assign-Statement verstehen (dauerhaft laufende Zuweisung, wie Kabel)
		[[SystemVerilog Konkatenation]]
		[[SystemVerilog Fallunterscheidungen]]
			>Simple kombinatorische Logik umsetzen können
			>Z.B. aus Schaltplan System-Verilog-Formel schreiben
	[[SystemVerilog für sequentielle Logik]]
		[[SystemVerilog Clock Signal]]
		[[SystemVerilog always Block]]
			>Funktionsweise always_comb-Block verstehen (auch konstante Zuweisung, erlaubt aber if-Statements etc...)
			>Lernen was alles in einen always_comb Block kann
			>Unterschied sequentielle/parallele Zuweisung verstehen
			>Warten auf Ereignisse mit always_comb-Blöcken verstehen und benutzen können (`@posedge CLK`)
		[[SystemVerilog Speicherelemente]]
			>D-Flip-Flops etc... verstehen und umsetzen können
			>Synchrone sequentielle Logik in SystemVerilog umsetzen können
		[[SystemVerilog Pipelines]]
			>Pipelines in SystemVerilog umsetzen können
	[[SystemVerilog für Zustandsautomaten]]
		>Gegebene Automaten in SystemVerilog umsetzen können
		>Aus SystemVerilog-Code Automaten ablesen können
	[[SystemVerilog für parametrisierte Module]]
		>Parametrisierte Module schreiben können
		[[SystemVerilog iterative Instanziierung]]
			>Submodule generativ instanziieren können
	[[SystemVerilog für Testumgebungen]]
		>Testbenches schreiben können
		>Selbsttestend und nicht selbsttestend
		>Unterschied Testbench und Modul verstehen
		[[Verzögerungen in SystemVerilog]]
	[[SystemVerilog Speicherfelder]]
		[[SystemVerilog RAM]]
			>RAM in SystemVerilog umsetzen können
		[[SystemVerilog ROM]]
			>ROM in SystemVerilog umsetzen können
***
[[Zahlensysteme]]
	[[Binärsystem]]
		[[Potenzen]]
			>Zweierpotenzen bis $2^{12}$ oder so
		[[Größenfaktoren]]
			>Größenfaktoren (Kibi und Kilo, Mebi und Mega, etc...) ($2^{10} und 10^{3}, 2^{20} und 10^{6}$, etc...)
		[[Teile von Bitfolgen]]
			>Namen für Teile von Bitfolgen (Bit, Nibble xD, Byte etc...)
		[[Addition von Binärzahlen]]
			>Binärzahlen addieren und subtrahieren können
			[[Bitbreitenerweiterung]]
	[[Umrechnen zwischen Zahlensystemen]]
		>Alle Darstellungen verstehen und umrechnen können
		[[Nibble-Werte]]
			>Nibble-Werte/drei-Bit-Werte im Idealfall auswendig lernen
	[[Vorzeichenloses Stellenwertsystem]]
	[[Vorzeichenbehaftete Binärzahlen]]
		[[Zweierkomplement]]
		[[Vorzeichen und Betrag]]
	[[Reelle Zahlen in Binärdarstelllung]]
		[[Vorzeichenloses Stellenwertsystem mit Nachkommastellen]]
		[[IEEE 754]]
***
[[Logische Schaltungen]]
	[[Arten von logischen Schaltungen]]
		[[Kombinatorische Logik]]
			>Eigenschaften wissen
		[[Sequentielle Logik]]
			>Eigenschaften wissen/Unterschied zu kombinatorischer Logik
			>Verschiedene Speicherelemente und Funktionsweisen kennen
			>Eigene Speicherelemente basteln können
			>Verschiedene Latches anhand eines Timing-Diagramms unterscheiden können
			[[Bistabile Grundschaltung]]
			[[SR-Latch]]
			[[JK-Latch]]
			[[D-Latch]]
			[[D-Flip-Flop]]
			[[Vergleich D-Latch mit D-Flip-Flop]]
			[[Flip-Flops mit Taktfreigabe]]
			[[Zurücksetzbare Flip-Flops]]
			[[Synchron Sequentielle Logik]]
				>Allgemeine Regeln für synchron sequentielle Logik verstehen und befolgen können
				>Eigene synchron sequentielle Logik basteln können
				>Funktionsweise asynchroner Eingänge verstehen
				[[Metastabilität]]
	[[Kombinatorische Grundelemente]]
		[[Logikgatter]]
			>Funktionsweise aller Logikgatter wissen/aus Gleichung Schaltnetz bauen können
			>Auch Funktionsweise Multiplexer/Decoder
		[[Zweistufige Logik]]
			>Zweistufige Logik aufstellen können
		[[Multiplexer]]
		[[Decoder]]
	[[Physik in logischen Schaltungen]]
		[[Spannungen als Logikpegel]]
			>$V_{OH}, V_{OL}, V_{IH}, V_{IL}, NM_H, NM_L$ verstehen und mithilfe von gegebenen Werten vielleicht ausrechnen können
		[[Feldeffekt-Transistoren]]
			>n- und p-Silizium
			>Funktionsweise und Aufbau n- und p-MOS Transistor
		[[CMOS-Schaltungen]]
			>CMOS-Schaltungen für beliebige Formeln erstellen
			>Pseudo-nMOS Schaltungen verstehen/basteln können
		[[Transmissionsgatter]]
			>Transmissionsgatternetze für beliebige Formeln erstellen
		[[Leistungsaufnahme]]
			>Unterschied dynamische/statische Leistungsaufnahme
	[[Zeitverhalten]]
		>Verständnis für $t_{pd}$ und $t_{cd}$ haben
		>Beides ausrechnen können
		>Timing-Diagramme ausfüllen können
		[[Störimpulse (Glitches)]]
			>Mithilfe von Karnaugh-Diagrammen Glitches in einer Schaltung erkennen und beheben können
			>Glitches in einem Timing-Diagramm erkennen
***
[[Boole'sche Gleichungen]]
	>Aufbau Boole'scher Gleichungen wissen
	>(Literal, Komplement etc...)
	>Funktionsweise und Aufbau Minterm/Maxterm, KNF/DNF
	>Schnell und zuverlässig aufstellen können
	[[Operatorpräzedenz]]
	[[Disjunktive Normalform (DNF)|Disjunktive Normalform]]
		[[Minterm]]
	[[Konjunktive Normalform (KNF)]]
		[[Maxterm]]
	[[Logikminimierung]]
		[[Boole'sche Algebra]]
			>Unterschied Axiom/Theorem und Bedeutung Dualität wissen 
			>Axiome/Theoreme zuverlässig anwenden können um Funktionen zu minimieren! 
			>DeMorgan zuverlässig anwenden können
			[[Bubble Pushing]]
				>Bubble Pushing anwenden können
			[[Mehrwertige Logik]]
				>Verständnis für X und Z
				>Vielleicht aus Wahrheitstafeln von einfachen Gattern Wahrheitstafeln von kleinen Schaltungen gestalten können
		[[Karnaugh Diagramme]]
			>Zuverlässig aufstellen und ablesen können
			>Min- und Maxterme ablesen können
			>Min- und Maxterme eintragen können
			>Don't Cares eintragen können
			[[Graycode]]
		[[Algorithmische Logikminimierung]]
			>Grobe Funktionsweise und Merkmale beider Verfahren kennen
***
[[Arithmetische Grundschaltungen]]
	[[Shifter]]
		>Verschiedene Shift-Arten und ihre Bedeutungen (durch zwei teilen, mit zwei multiplizieren etc...) kennen
	[[Addierer]]
	[[Ripple-Carry-Adder (RCA)]]
		>Funktionsweise und Aufbau können (Halbaddierer/Volladdierer)
		>Auch Subtrahierer-Variante verstehen
	[[Conditional Sum Adder (CSA)]]
		>Funktionsweise und Aufbau können
	[[Carry Lookahead Adder (CLA)]]
		>Funktionsweise und Aufbau können + Verständnis für Zeitverhalten haben!
***
[[Parallelität]]
	>Pipeline Timing-Bedingungen überprüfen können
	>Pipeline Frequenz bestimmen können
	>Pipeline Timing-Bedingungen wiederherstellen können
	>Durchsatz/Latenz berechnen können
	>Arten der Parallelität kennen
	>Begrifflichkeiten verstehen (Unterschied Durchsatz/Latenz zum Beispiel)
***
[[Endliche Zustandsautomaten]]
	>Eigene Moore und Mealy-Automaten zu gegebenen Aufgabenstellungen basteln können
	[[Hardware für endliche Zustandsautomaten]]
		>Zustandsübergangstabellen/Ausgabetabellen $\leftrightarrow$ Automaten
		>Aus einem gegebenen Automaten eine Schaltung erstellen können (mithilfe von Karnaugh-Diagrammen)
	[[Moore vs Mealy]]
		>Funktionsweise und Unterschied Moore/Mealy-Automat verstehen
	>Vor- und Nachteile Moore/Mealy-Automat kennen
	[[Zerlegen von Zustandsautomaten]]
***
[[Speicherfelder]]
	>Speicherfeld Aufbau und Formeln für Größe verstehen und anwenden können
	>Funktionsweise verstehen (wie wird geschrieben und gelesen?)
	[[Speicherarten]]
		[[Random Access Memory (RAM)]]
			>Unterschied DRAM/SRAM verstehen (wie wird gespeichert?)
			[[Dynamic RAM (DRAM)]]
			[[Static RAM (SRAM)]]
		[[Read-Only Memory (ROM)]]
			>Funktionsweise ROM verstehen
			>Logik mit ROM verstehen/umsetzen können
			>ROM Punktnotation verstehen/benutzen können
			[[Flash]]
				>Funktionsweise von Flash-Zellen verstehen
[[Logikfelder]]
	[[Programmable Logic Array (PLA)]]
		>Funktionsweise PLA verstehen
	[[Field Programmable Gate Array (FPGA)]]
		>Funktionsweise FPGA verstehen, Aufbau können?
		>Funktionsweise einzelner Teile können?
