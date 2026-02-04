---
tags:
  - foliensatz/01
  - cleaned
---

## Wesentliche Techniken

- Hierarchie (Hierarchy)
	- Aufteilen eines Systems in Module und Untermodule
- Modularität (Modularity)
	- wohldefinierte Schnittstellen und Funktionen
- Regularität (Regularity)
	- bevorzuge einheitliche Lösungen für einfachere Wiederverwendbarkeit

### Beispiel: Fahrrad

- Alltagsbeispiel für die Anwendung der drey Y's
- Komplexer Gebrauchsgegenstand
- Entwicklung begann im 19. Jahrhundert
- Verschiedenste historische Modelle und Bauweisen
- Heutige Fahrräder weitesgehend standardisiert durch Normen und Industriestandards

#### Hierarchie

Ein Fahrrad lässt sich eindeutig in verschiedene wohldefinierte, separate Module unterteilen, die sich wiederum in Untermodule unterteilen lassen

##### Zerlegung in Module

An diesem Bild sieht man wie sich ein Fahrrad in Module unterteilen lässt...

![[Screenshot 2025-10-17 at 09.04.32.png]]

##### Zerlegung in Untermodule

...und wie sich eines der Module (die Schaltung) wiederum in verschiedene Untermodule unterteilen lässt

![[Screenshot 2025-10-17 at 09.05.09.png]]

## Modularität

Alle Module des Fahrrads erfüllen eine fest definierte Funktion und lassen sich bei Bedarf gegen andere Teile/Module austauschen, solange diese die gleiche Funktion erfüllen

- Funktion der Räder
	- Übertragung des Gewichts von Fahrer:in an Boden und von Drehung zu Vorwärtsbewegung
- Funktion der Schaltung
	- Weitergabe von Drehung der Kurbel an Reifen als Getriebe
- Im Idealfall sind Funktionen unabhängig und beeinflussen sich nicht
- Schnittstelle zwischen Hinterrad und Schaltung
	- Gemeinsame Achse

## Regularität

Da verschiedene Radmodelle oft trotzdem die gleiche Schnittstelle zwischen den Komponenten haben (z.B. dass das Hinterrad und die Schaltung sich eine gemeinsame Achse teilen), ist eine hohe Regularität gegeben. Dadurch lassen sich viele verschiedene Schaltungen für das gleiche Rad verwenden.

- Verschiedene Schaltungen für gleiche Räder
	- Voraussetzung: Kompatibilität mit Kassette an Achse
- Unterschiedliche Lenker an gleichen Rahmen
- Gleicher Rahmen für unterschiedliche Räder
	- Voraussetzung: Raddurchmesser und -breite passend
- Voraussetzung für Massenproduktion, einfache Reparatur und Modifikation

