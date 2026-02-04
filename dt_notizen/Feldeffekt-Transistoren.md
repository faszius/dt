---
tags:
  - foliensatz/03
  - cleaned
aliases:
  - Transistoren
  - Transistor
---

## Transistoren

- Logikgatter werden üblicherweise aus Transistoren aufgebaut
	- Heute überwiegend Feldeffekttransistor (FET, "Field Effect Transistor")
- Transistoren sind spannungsgesteuerte Schalter
	- Zwei Anschlüsse (Source $s$ und Drain $d$) werden je nach Spannung am dritten Eingang (Gate $g$) verbunden oder getrennt ![[Screenshot 2025-10-29 at 21.46.25.png]]

## Der Feldeffekt

![[Screenshot 2025-10-29 at 21.50.30.png]]

- Wir betrachten zwei metallische Streifen mit einer dünnen isolierenden Zwischenlage
- Die Streifen bilden einen Plattenkondensator (Kapazität $C$)
- Die Steuerspannung $V_g$ am Kondensator lädt diesen auf
- Wir haben jeweils Ladung $Q = C \cdot V_g$ auf beiden Seiten (gegensätzliche Ladung)
- Die Steuerspannung $V_g$ beeinflusst die Menge der freien Ladungsträger, also den Widerstand $R_{sd}$
- Dadurch gewinnen wir etwa $10^{14}$ zusätzliche freie Ladungsträger pro Kubikzentimeter für $V_g = 1V$
- Jedoch haben Metalle schon etwa $10^{22}$ freie Ladungsträger pro Kubikzentimeter
- Halbleiter haben aber nur etwa $10^{13}$ freie Ladungsträger pro Kubikzentimeter
- Bei Halbleitern wird der Feldeffekt technisch nutzbar!

## Silizium-basierte Halbleiter

- Reines Silizium ist ein schlechter Leiter (es hat keine freien Ladungsträger)
- Dotierung ermöglicht aber das gezielte Einbringen freier Ladungsträger
- Wir unterscheiden zwischen n-Typ Silizium und p-Typ Silizium
	- n-Typ Silizium hat zusätzliche Elektronen
	- p-Typ Silizium hat weniger Elektronen

| Typ | Freie Ladungsträger | Dotierte Elemente        |
| --- | ------------------- | ------------------------ |
| n   | Elektronen (-)      | Arsen (As), Phosphor (P) |
| p   | Löcher (+)          | Bor (B), Gallium (Ga)    |

![[Screenshot 2025-10-29 at 21.59.27.png]]

### P/N-Übergang = Diode

- Eine Diode ist der Übergang zwischen p-Typ und n-Typ Silizium 
  ![[Screenshot 2025-10-29 at 21.59.59.png]]
- Wenn p- und n-Silizium in Berührung kommen, entsteht ein kleiner Bereich, in dem die Elektronen des n-Silizium die Löcher des p-Silizium füllen, sodass in diesem Bereich keine freien Ladungsträger sind
  ![[Screenshot 2025-10-30 at 12.05.51.png]]
- Die Schwellenspannung heißt $V_{th}$, die Spannung an der Anode $V_A$, die Spannung an der Kathode $V_C$
- Vorwärtsspannung
	- Wenn $V_{AC} = V_A - V_C > V_{th}$
	- Dann entsteht ein Stromfluss von Anode zu Kathode
	  ![[Screenshot 2025-10-30 at 12.09.08.png]]
- Sperrspannung
	- Wenn $V_{AC} = V_A - V_C < V_{th}$
	- Dann haben wir keinen Stromfluss
	  ![[Screenshot 2025-10-30 at 12.09.35.png]]

## MOS Feldeffekttransistoren (MOSFETs)

- Metalloxid-Halbleiter (MOS) Transistoren
	- Undotiertes Silizium (früher Metallschicht) für Gate
	- Oxid (Siliziumoxid = Glas) für Isolator
	- Dotiertes Silizium für Substrat und Anschlüsse (Source, Drain)
- nMOS Transistor:
  ![[Screenshot 2025-10-30 at 12.12.42.png]]
- pMOS Transistor:
  ![[Screenshot 2025-10-30 at 12.13.03.png]]

### nMOS

- Wenn am Gate keine Spannung anliegt (Gate = 0), ist der Transistor ausgeschaltet
	- Keine Source-Drain Verbindung
	  ![[Screenshot 2025-10-30 at 12.16.21.png]]
- Wenn am Gate eine Spannung anliegt (Gate = 1), ist der Transistor eingeschaltet
	- Leitfähiger Source-Drain Kanal
	  ![[Screenshot 2025-10-30 at 12.16.36.png]]
- Beim nMOS-Transistor sind die Majoritätsladungsträger Elektronen
	- Leiten 0en gut von Source nach Drain weiter

#### Erklärung

- Wenn am Gate keine Spannung anliegt, existiert kein Spannungsunterschied zwischen dem p-Silizium und dem Gate (da beide auf GND gesetzt sind)
- Dadurch befinden sich das n-Silizium und p-Silizium in einem stabilen Zustand, in dem keine Elektronen ausgetauscht werden (siehe Dioden)
- Wenn am Gate eine Spannung anliegt, entsteht ein Spannungsunterschied, und durch den Feldeffekt sammeln sich im Gate Löcher und im p-Silizium am Gate Elektronen
- Dadurch, dass sich im p-Silizium am Gate jetzt Elektronen sammeln, entsteht eine "Brücke" an Elektronen zwischen Source und Drain, sodass Elektronen zwischen den beiden fließen können
- Jedoch ist die Brücke nicht "stark" genug, als dass genug Elektronen von Source nach Drain fließen, um eine eindeutige $1$ darzustellen - es ist aber auf jeden Fall keine $0$ mehr
- Dadurch können nMOS-Transistoren sehr gut 0en darstellen (es fließen absolut keine Elektronen), jedoch nicht so gut 1en (es fließen ein paar Elektronen)

### pMOS

-  Wenn am Gate eine Spannung anliegt (Gate = 1), ist der Transistor ausgeschaltet
	- Keine Source-Drain Verbindung
	  ![[Screenshot 2025-10-30 at 12.35.40.png]]
- Wenn am Gate keine Spannung anliegt (Gate = 0), ist der Transistor eingeschaltet
	- Leitfähiger Source-Drain Kanal
	  ![[Screenshot 2025-10-30 at 12.35.52.png]]
- Beim nMOS-Transistor sind die Majoritätsladungsträger Löcher
	- Leiten 1en gut von Source nach Drain weiter

#### Erklärung

- Wenn am Gate eine Spannung anliegt, existiert kein Spannungsunterschied zwischen dem p-Silizium und dem Gate (da an beiden eine Spannung anliegt)
- Dadurch befinden sich das n-Silizium und p-Silizium in einem stabilen Zustand, in dem keine Elektronen ausgetauscht werden (siehe Dioden)
- Wenn am Gate keine Spannung anliegt, entsteht ein Spannungsunterschied, und durch den Feldeffekt sammeln sich im Gate Elektronen und im p-Silizium am Gate Löcher
- Dadurch, dass sich im p-Silizium am Gate jetzt Löcher sammeln, entsteht eine "Brücke" an Elektronen zwischen Source und Drain, sodass Löcher zwischen den beiden fließen können
- Im Ruhezustand fließen meistens jedoch trotzdem ein paar Löcher zwischen Source und Drain, da am Gate und am n-Silizium nicht genau die gleiche Spannung anliegt (z.B. durch Störsignale) - dadurch entsteht trotz allem ein leichter Feldeffekt
- Dadurch können nMOS-Transistoren sehr gut 1en darstellen (es fließen sehr viele Löcher), jedoch nicht so gut 1en (es fließen fast keine Löcher)

### MOSFET Schaltverhalten

![[Screenshot 2025-10-30 at 12.45.05.png]]

