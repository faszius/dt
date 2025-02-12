
>[!Important] Wichtig (sehr)
>Ich erhebe absolut gar kein Anspruch auf Vollständigkeit und/oder Richtigkeit
>Alles was ich sage stammt nur aus meiner Erfahrung, das Modul schon einmal belegt zu haben und sich als Tutor noch ein zweites Mal mit dem Stoff beschäftigt zu haben

## Komplexität, Abstraktion Und Schichtenmodell

[[dt_folien_01_v1.pdf#page=34|dt_folien_01_v1, page 34]]

Verständnis für die Begriffe aus der Vorlesung, kann vielleicht eine kleine Wissensfrage ( #Klausuraufgabe) sein oder so

## Zahlensysteme

### Binärzahlen

#### Allgemeines

[[dt_folien_01_v1.pdf#page=52|dt_folien_01_v1, page 52]]

Zweierpotenzen bis $2^{12}$ oder so
Größenfaktoren (Kibi und Kilo, Mebi und Mega, etc...) ($2^{10} und 10^{3}, 2^{20} und 10^{6}$, etc...)
Namen für Teile von Bitfolgen (Bit, Nibble xD, Byte etc...)

#### Darstellungen

Normal (auch mit Kommata)
[[dt_folien_01_v1.pdf#page=64|dt_folien_01_v1, page 64]]
Zweierkomplement
[[dt_folien_02_v1.pdf#page=14|dt_folien_02_v1, page 14]]
Vorzeichen und Betrag (auch mit Kommata)
[[dt_folien_13_v1.pdf#page=15|dt_folien_13_v1, page 15]]
Gleitkommadarstellung
[[dt_folien_13_v1.pdf#page=27|dt_folien_13_v1, page 27]]

Alle Darstellungen verstehen

#### Rechnen Mit Binärzahlen

Addieren
Subtrahieren (Dafür zweite Binärzahl in eine negative Zweierkomplementzahl umrechnen!)

### Umrechnungen

Jedes Zahlensystem in's Dezimalsystem (mit Horner-Schema, erfordert allgemeines Verständnis wie Zahlensysteme mit anderen Basen funktionieren!)

#### Dezimal $\leftrightarrow$ Binär

In normale Binärzahlen
In Zweierkomplement Binärzahlen
In Vorzeichen Betrag Binärzahlen
In Gleitkomma Binärzahlen

**Verfahren**
Durch zwei Teilen
Größte Zweierpotenz abziehen
Für Gleitkommazahlen komplexere Umrechnungsschritte

#### Binär $\leftrightarrow$ Hexal/Oktal

Dafür Nibble-Werte/drei-Bit-Werte im Idealfall auswendig lernen
[[dt_folien_02_v1.pdf#page=6|dt_folien_02_v1, page 6]]

## Elektrotechnik-Zeugs

### Spannungen Als Logikpegel

[[dt_folien_03_v1.pdf#page=5|dt_folien_03_v1, page 5]]

$V_{OH}, V_{OL}, V_{IH}, V_{IL}, NM_H, NM_L$ verstehen und mithilfe von gegebenen Werten vielleicht ausrechnen können
$V_{DD}$

### Transistoren

[[dt_folien_03_v1.pdf#page=14|dt_folien_03_v1, page 14]]

n- und p-Silizium
Funktionsweise und Aufbau n- und p-MOS Transistor

### CMOS

[[dt_folien_03_v1.pdf#page=24|dt_folien_03_v1, page 24]]

CMOS-Schaltungen für beliebige Formeln erstellen
Pseudo-nMOS Schaltungen verstehen/basteln können

### Transmissionsgatter

[[dt_folien_03_v1.pdf#page=32|dt_folien_03_v1, page 32]]

Transmissionsgatternetze für beliebige Formeln erstellen

### Leistungsaufnahme

[[dt_folien_03_v1.pdf#page=33|dt_folien_03_v1, page 33]]

Unterschied dynamische/statische Leistungsaufnahme
Formeln auswendig lernen bezweifle ich

## Logikminimierung

### Boole'sche Algebra

[[dt_folien_04_v1.pdf#page=4|dt_folien_04_v1, page 4]]
[[dt_folien_05_v1.pdf#page=4|dt_folien_05_v1, page 4]]

Aufbau Boole'scher Gleichungen wissen
(Literal, Komplement etc...)

Funktionsweise und Aufbau Minterm/Maxterm, KNF/DNF
Schnell und zuverlässig aufstellen können

Unterschied Axiom/Theorem und Bedeutung Dualität wissen 
Axiome/Theoreme zuverlässig anwenden können um Funktionen zu minimieren! 
DeMorgan zuverlässig anwenden können
Bestimmt eine #Klausuraufgabe

### Karnaugh-Diagramme

[[dt_folien_06_v1.pdf#page=4|dt_folien_06_v1, page 4]]

Zuverlässig aufstellen und ablesen können
Min- und Maxterme ablesen können
Min- und Maxterme eintragen können
Don't Cares eintragen können
Bestimmt eine #Klausuraufgabe

### Algorithmische Logikminimerung

Grobe Funktionsweise und Merkmale beider Verfahren kennen
(vielleicht eine kleine Wissensfrage #Klausuraufgabe )

## Logikgatter/Schaltungen

Funktionsweise aller Logikgatter wissen/aus Gleichung Schaltnetz bauen können
[[dt_folien_02_v1.pdf#page=22|dt_folien_02_v1, page 22]]

Auch Funktionsweise Multiplexer/Decoder, vielleicht anfangs schwer zu verstehen aber wichtig!
[[dt_folien_05_v1.pdf#page=37|dt_folien_05_v1, page 37]]
[[dt_folien_05_v1.pdf#page=40|dt_folien_05_v1, page 40]]

### Tricks Mit Logikgattern

#### AND

Wie kontrolliert man mit einem Steuersignal $s$, ob das Signal $A$ durchgelassen wird?
Wenn man $A$ und $s$ verundet, wird $A$ nur genau dann durchgelassen, wenn $s = 1$

#### XOR

Wie kann man überprüfen, ob die Anzahl an 1en in einer Binärzahl $A$ gerade/ungerade ist?
$a_1 \oplus a_2 \oplus \ldots \oplus a_n$ ist genau dann 1, wenn die Anzahl an 1en ungerade ist
Wenn man weiß, wie lang die Binärzahl ist, kann man damit auch bestimmen, ob die Anzahl der 0en gerade oder ungerade ist
Wie kann man überprüfen, ob zwei Bits gleich sind? $A \oplus B = 0$ genau dann wenn $A = B$

#### Multiplexer

Gegeben eine Wahrheitstafel, wie erstelle ich mit beliebigen Gattern eine passende Schaltung? Mit einem Multiplexer möglich

#### Decoder

Gegeben eine Wahrheitstafel, wie erstelle ich mit beliebigen Gattern eine passende Schaltung? Mit einem Decoder + OR-Gatter möglich

#### Bubble Pushing

[[dt_folien_05_v1.pdf#page=28|dt_folien_05_v1, page 28]]

Bubble Pushing anwenden können

### Zweistufige Logik

[[dt_folien_05_v1.pdf#page=34|dt_folien_05_v1, page 34]]

Zweistufige Logik aufstellen können

### Kombinatorische Logik

[[dt_folien_04_v1.pdf#page=12|dt_folien_04_v1, page 12]]

Eigenschaften wissen

### Zeitverhalten Von Schaltungen

Verständnis für $t_{pd}$ und $t_{cd}$ haben
Beides ausrechnen können
Sehr wichtig für Pipelines!

Timing-Diagramme ausfüllen können

#### Glitches

Mithilfe von Karnaugh-Diagrammen Glitches in einer Schaltung erkennen und beheben können
(Glitches in einem Timing-Diagramm erkennen)

### Mehrwertige Logik

Verständnis für X und Z
Vielleicht aus Wahrheitstafeln von einfachen Gattern Wahrheitstafeln von kleinen Schaltungen gestalten können
Ich _glaube_ dass euch die mehrwertigen Wahrheitstafeln für einfache Gatter gestellt werden

## Arithmetische Schaltungen

[[dt_folien_07_v1.pdf#page=5|dt_folien_07_v1, page 5]]

### Shifter

Verschiedene Shift-Arten und ihre Bedeutungen (durch zwei teilen, mit zwei multiplizieren etc...)

### Ripple-Carry-Adder

Funktionsweise und Aufbau können (Halbaddierer/Volladdierer)
Auch Subtrahierer-Variante verstehen

### Conditional Sum Adder (CSA)

[[dt_folien_08_v1.pdf#page=7|dt_folien_08_v1, page 7]]

Funktionsweise und Aufbau können

### Carry-Lookahead-Adder

[[dt_folien_08_v1.pdf#page=8|dt_folien_08_v1, page 8]]

Funktionsweise und Aufbau können
\+ Verständnis für Zeitverhalten haben!

## Sequentielle Logik

[[dt_folien_08_v1.pdf#page=15|dt_folien_08_v1, page 15]]

Eigenschaften wissen/Unterschied zu kombinatorischer Logik

### Speicherelemente

[[dt_folien_08_v1.pdf#page=18|dt_folien_08_v1, page 18]]

Verschiedene Speicherelemente und Funktionsweisen kennen
Eigene Speicherelemente basteln können (beliebte #Klausuraufgabe)
D-Flip-Flop und D-Latch anhand eines Timing-Diagramms unterscheiden können (Kann gut eine #Klausuraufgabe sein)

### Synchron Sequentielle Logik

[[dt_folien_08_v1.pdf#page=29|dt_folien_08_v1, page 29]]

Aufbau und Regeln synchron sequentieller Logik kennen, eigene synchron sequentielle Logik basteln können
Funktionsweise asynchroner Eingänge verstehen

#### Zeitverhalten Von Synchroner Sequentieller Logik

[[dt_folien_09_v1.pdf#page=19|dt_folien_09_v1, page 19]]

Pipeline Timing-Bedingungen überprüfen können
Pipeline Frequenz bestimmen können
Pipeline Timing-Bedingungen wiederherstellen können
Durchsatz/Latenz berechnen können

#### Parallelität

[[dt_folien_09_v1.pdf#page=28|dt_folien_09_v1, page 28]]

(Arten der Parallelität kennen)
Begrifflichkeiten verstehen (Unterschied Durchsatz/Latenz zum Beispiel)

## Automaten

[[dt_folien_10_v2.pdf#page=5|dt_folien_10_v2, page 5]]

Funktionsweise und Unterschied Moore/Mealy-Automat verstehen
Vor- und Nachteile Moore/Mealy-Automat kennen
Eigene Moore und Mealy-Automaten zu gegebenen Aufgabenstellungen basteln können
Zustandsübergangstabellen/Ausgabetabellen $\leftrightarrow$ Automaten
Aus einem gegebenen Automaten eine Schaltung erstellen können (mithilfe von Karnaugh-Diagrammen)

## Speicherfelder

[[dt_folien_12_v1.pdf#page=4|dt_folien_12_v1, page 4]]

Speicherfeld Aufbau und Formeln für Größe verstehen und anwenden können
Funktionsweise verstehen (wie wird geschrieben und gelesen?)
Unterschied DRAM/SRAM verstehen (wie wird gespeichert?)

### ROM

Funktionsweise ROM verstehen
Logik mit ROM verstehen/umsetzen können
ROM Punktnotation verstehen/benutzen können

### Flash

Funktionsweise von Flash-Zellen verstehen

## Logikfelder

[[dt_folien_12_v1.pdf#page=29|dt_folien_12_v1, page 29]]

Funktionsweise PLA verstehen
#TODO ASIC
Funktionsweise FPGA verstehen, Aufbau können?
Funktionsweise einzelner Teile können?

## SystemVerilog

Auch nochmal angucken: SystemVerilog Referenz auf Moodle!

### Darstellung Von Numerischen Literalen

[[dt_folien_01_v1.pdf#page=66|dt_folien_01_v1, page 66]]

### Kombinatorische Logik

[[dt_folien_04_v1.pdf#page=17|dt_folien_04_v1, page 17]]

Simple kombinatorische Logik umsetzen können
Z.B. aus Schaltplan System-Verilog-Formel schreiben

### Module

[[dt_folien_04_v1.pdf#page=17|dt_folien_04_v1, page 17]]

Aufbau eines Moduls können, Module selbst schreiben können
Submodule instanziieren und verwenden können 
Einfache Module ohne Probleme selbst schreiben (z.B. Eingänge A und B, Ausgang Y, berechnet irgendeine Formel mit A und B)

### Multiplexer

Multiplexer in SystemVerilog umsetzen

### Datentypen

[[dt_folien_07_v1.pdf#page=20|dt_folien_07_v1, page 20]]

Verschiedene Datentypen kennen und verwenden können
Vor allem Vektoren verstehen! (auch Unterschied zu Arrays)
Wichtig bei Vektoren: Operationen auf Vektoren und **Unterschied bitweise/logische/unäre Operationen!**

### Variablenzuweisungen

#### Assign

Funktionsweise assign-Statement verstehen (dauerhaft laufende Zuweisung, wie Kabel)

#### always_comb

[[dt_folien_09_v1.pdf#page=14|dt_folien_09_v1, page 14]]

Funktionsweise always_comb-Block verstehen (auch konstante Zuweisung, erlaubt aber if-Statements etc...)
Lernen was alles in einen always_comb Block kann
Unterschied sequentielle/parallele Zuweisung verstehen

### SystemVerilog Für Sequentielle Logik

[[dt_folien_09_v1.pdf#page=17|dt_folien_09_v1, page 17]]

Warten auf Ereignisse mit always_comb-Blöcken verstehen und benutzen können (`@posedge CLK`)
D-Flip-Flops etc... verstehen und umsetzen können
Allgemeine Regeln für synchron sequentielle Logik verstehen und befolgen können
Synchrone sequentielle Logik in SystemVerilog umsetzen können

### Automaten

[[dt_folien_10_v2.pdf#page=16|dt_folien_10_v2, page 16]]

Gegebene Automaten in SystemVerilog umsetzen können
Aus SystemVerilog-Code Automaten ablesen können

### Parametrisierte Module

[[dt_folien_11_v1.pdf#page=17|dt_folien_11_v1, page 17]]

Parametrisierte Module schreiben können
Submodule generativ instanziieren können

### Testbenches

[[dt_folien_11_v1.pdf#page=26|dt_folien_11_v1, page 26]]

Testbenches schreiben können
Selbsttestend und nicht selbsttestend
Unterschied Testbench und Modul verstehen

### Speicherfelder

[[dt_folien_12_v1.pdf#page=19|dt_folien_12_v1, page 19]]

RAM in SystemVerilog umsetzen können
ROM in SystemVerilog umsetzen können

