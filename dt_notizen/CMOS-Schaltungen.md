---
tags:
  - foliensatz/03
  - cleaned
aliases:
  - CMOS
---

## CMOS-Schaltungen

- pMOS Transistoren leiten 1en "gut" von Source nach Drain weiter
	$\Rightarrow$ Source an $V_{DD}$ anschließen
- nMOS Transistoren leiten 0en "gut" von Source nach Drain weiter
	$\Rightarrow$ Source an GND anschließen
- So entsteht Complementary Metal-Oxide-Semiconductor (CMOS) Logik
	- Im Pull-U**p**-Netz haben wir **p**MOS-Transistoren
	- Im Pull-Dow**n**-Netz haben wir **n**MOS-Transistoren

>[!Important]
>Wichtig: mit unserem jetzigen Wissen können wir nur _negierte_ logische Formeln als CMOS-Schaltung umsetzen - also z.B. $Y = \overline{A}$, $Y = \overline{A \land B}$ oder $Y = \overline{A \lor (B \oplus C)}$. Eine nicht-negierte logische Formeln wie $Y = A \lor B$ ist noch *nicht* möglich!

![[Screenshot 2025-10-30 at 12.47.35.png]]

## CMOS-Gatter

### NOT

`NOT`-Gatter:
![[Screenshot 2025-10-30 at 12.48.15.png]]

Schaltverhalten:
![[Screenshot 2025-10-30 at 12.48.28.png]]

CMOS-Schaltung:
![[Screenshot 2025-10-30 at 12.49.10.png]]

- Um in CMOS ein `NOT`-Gatter zu bauen, setzen wir im Pull-Up-Netz ein pMOS-Gatter, und im Pull-Down-Netz ein nMOS-Gatter, welche beide von A gesteuert werden

### NAND

`NAND`-Gatter:
![[Screenshot 2025-10-30 at 12.56.12.png]]

Schaltverhalten:
![[Screenshot 2025-10-30 at 12.56.28.png]]

CMOS-Schaltung:
![[Screenshot 2025-10-30 at 12.56.45.png]]

- Um zwei Literale miteinander zu verunden, müssen das Pull-Up-Netz und das Pull-Down-Netz einander ergänzen
- Dafür schalten wir im Pull-Up-Netz zwei pMOS-Gatter _parallel_ (nebeneinander) und im Pull-Down-Netz zwei nMOS-Gatter _seriell_ (hintereinander)

### NOR (drei Eingänge)

![[Screenshot 2025-10-31 at 11.28.23.png]]

- Hier werden im Pull-Up-Netz die pMOS-Transistoren in Reihe geschaltet, um ein `OR` zu bekommen
- Dementsprechend werden im Pull-Down-Netz die nMOS-Transistoren parallel geschaltet

## Struktur eines CMOS-Gatters

- pMOS Parallelschaltungen im Pull-Up-Netz entsprechen im Pull-Down-Netz einer nMOS Serienschaltung (und vice versa)
- pMOS Serienschaltungen im Pull-Up-Netz entsprechen im Pull-Down-Netz einer nMOS Serienschaltung (und vice versa)

## Pseudo-nMOS-Gatter

- Wir können das Pull-Up-Netz durch einen schwachen, immer eingeschalteten pMOS ersetzen
- Das Pull-Up-Netz kann dann durch das Pull-Down-Netz "überstimmt" werden
- Nützlich, um lange Reihen von Transistoren zu vermeiden

![[Screenshot 2025-10-31 at 11.32.40.png]]

### Beispiel für Pseudo-nMOS-Gatter

- Pseudo-nMOS `NOR5`
- Verbraucht aber mehr Energie: schwacher Dauerkurzschluss bei $Y=0$

![[Screenshot 2025-10-31 at 11.33.36.png]]
