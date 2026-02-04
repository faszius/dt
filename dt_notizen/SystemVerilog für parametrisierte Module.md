---
tags:
  - foliensatz/11
  - cleaned
aliases:
  - Parameter
---

## Beispiel einer sequentiellen Schaltung: Zähler

- Erhöht sich bei jeder steigenden Taktflanke
- Dient zum Durchlaufen von Zahlen, Beispiel
	- 000, 001, 010, 011, 100, 101, 110, 111, 000, 001, ...
- Verwendung (Beispiele):
	- Displays von Digitaluhren, Programmzähler in einer CPU, ...
- Wie lassen sich [[Addierer]] und [[D-Flip-Flop|Register]] für beliebig viele Bits $N$ in SystemVerilog umsetzen?

## Parametrisierte [[SystemVerilog Module|Module]]

- Neben Ein- und Ausgaben kann eine Modulschnittstelle auch `parameter` definieren
- Parametrisierte Eigenschaften werden bei Instanziierung durch konkrete Werte ersetzt
	- Nach Synthese der Hardware und während Simulation nicht mehr änderbar
	- Vergleichbar mit C-Präprozessor oder Java-Generics
- Typische Parameter: Port-Breite, Speichertiefe, ...

### Beispiele

Parametrisierter Addierer:
![[Pasted image 20260116162253.png]]

Und wie dieser in einem counter instanziiert wird:
![[Pasted image 20260116162300.png]]

Parametrisiertes Register:
![[Pasted image 20260116162353.png]]

Bei allen Beispielen kann `N` bei der Instanziierung angegeben werden und wird dann überall mit dem angegebenen Wert ersetzt. Sonst behält `N` den definierten Standard-Wert
