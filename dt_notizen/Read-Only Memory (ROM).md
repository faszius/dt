---
tags:
  - foliensatz/12
  - "#MoC"
  - cleaned
aliases:
  - ROM
  - Read-Only Memory
  - Read Only Memory
---

## Read-Only Memory (ROM)

- Nicht flüchtig: Daten bleiben beim Ausschalten erhalten
- Schnelles Lesen, aber Schreiben ist unmöglich oder langsam
- Flash-Speicher in Digitalkameras, USB-Sticks und SSDs sind alles ROMs

Historisch als Festwertspeicher bezeichnet, da ROMs zum Zeitpunkt der Herstellung oder durch Brennen von Sicherungen einmalig beschrieben wurden. Sobald das ROM konfiguriert wurde, konnte es nicht erneut beschrieben werden. Neuere Arten von ROMs wie Flash-Speicher können mehrmals beschrieben werden.

## ROM Punktnotation

- Mithilfe der Punktnotation können wir kompakt darstellen, was in einem ROM gespeichert ist

Wenn wir folgendes Speicherfeld haben:
![[Pasted image 20260124113807.png]]

Dann sieht die dazugehörige Punktnotation so aus:
![[Pasted image 20260124113834.png]]

### Logik via ROM

Wir wollen die folgenden Logikfunktionen mit einem $2^2 \times 3$-Bit ROM implementieren:
- $X = AB$
- $Y = A+B$
- $Z = A \overline{B}$

Für jede Adresskombination setzen wir also einfach überall dort Punkte, wo die Formeln wahr sind:
![[Pasted image 20260124115430.png]]

Genau so können wir aus einem gegebenen ROM die Formeln ablesen:
![[Pasted image 20260124115629.png]]

In diesem Fall ist 
- $\text{Data}_2 = A_1 \oplus A_0$
- $\text{Data}_1 = \overline{A_1} + A_0$
- $\text{Data}_0 = \overline{A_1} \overline{A_0}$

#### In Speicherfeldern

In ein Speicherfeld geschrieben würde das ganze so aussehen:
![[Pasted image 20260124120150.png]]

#### Lookup-Table (LUT)

Wir können Wahrheitstabellen auch mit ROM speichern:
![[Pasted image 20260124120232.png]]

Das nennen wir dann Lookup-Table (LUT)

## Lesen

- Zum Lesen setzen wir die Bitline auf weak high und danach die Wordline auf 1. Wenn ein Transistor vorhanden ist, zieht dieser die Bitline auf $0$, sonst bleibt diese auf $1$.

![[Pasted image 20260124114343.png]]

## Flash

- Ein Beispiel für eine schreibbare ROM-Zelle ist [[Flash]]

