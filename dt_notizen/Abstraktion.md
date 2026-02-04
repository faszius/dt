---
tags:
  - foliensatz/01
  - cleaned
---

## Abstraktion

- Wichtiges und zentrales Konzept der Informatik
- Verstecken (für eine spezielle Aufgabe) "unnötiger" Details
- Verstehen der Abstraktionsebenen ist aber für alle Aufgaben hilfreich

### Beispiel

Folgendes ist ein gutes Beispiel für ein Schichtenmodell (am Beispiel eines Computers) mit verschiedenen Abstraktionsebenen. Je höher die Schicht, desto mehr wird abstrahiert.

![[Screenshot 2025-10-17 at 08.44.45.png]]

### Sinn Eines Schichtenmodells

Wesentliche Eigenschaften eines Schichtenmodells sind:
- Die untere Schicht erbringt Dienstleistungen für die nächste höhere Schicht
- Die obere Schicht nutzt nur die Dienste der nächst niedrigeren Schicht
- Es sind eindeutige Schnittstellen zwischen den Schichten definiert
- Vorteile einer sauberen Schichtenstruktur:
	- Austauschbarkeit einzelner Schichten, ohne benachbarte Schichten oder das gesamte System ändern zu müssen
	- Benutzer:in braucht nur die von ihm:ihr zu bearbeitende Schicht zu kennen 
	- Darunterliegende Schichten bilden eine fest definierte Funktionalität
	- Für manche Aufgaben ist eine genauere Kenntnis der unteren Schichten dennoch notwendig (z.B. Programmierung von Gerätetreibern)
- Ein Nachteil ist eine ggf. geringere Leistungsfähigkeit des Systems
