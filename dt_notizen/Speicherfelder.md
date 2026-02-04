---
tags:
  - foliensatz/12
  - cleaned
Related:
  - "[[Speicherarten]]"
aliases:
  - Speicherfeld
---

## Speicherfeld

- 2-dimensionales Array von Bitzellen
- Jede Bitzelle speichert ein Bit
- $N$ Adressbits und $M$ Datenbits
	- $2^N$ Zeilen und $M$ Spalten
	- Tiefe: Anzahl der Zeilen (Anzahl der Wörter)
	- Breite: Anzahl der Spalten (Wortbreite)
	- Größe: Tiefe $\times$ Breite = $2^N \times M$ Bits

## Beispiel

![[Screenshot 2026-01-24 at 10.51.33.png]]

- $2^2 \times 3$-Bit Array
- Anzahl der Wörter: 4
- Wortbreite: 3 Bits
- Beispiel: das 3-Bit Wort, das an der Adresse $10$ gespeichert ist, lautet $100$

So würde ein $10^2 \times 32$-Bit Array aussehen:
![[Screenshot 2026-01-24 at 10.53.49.png]]

## Wordline

- Vergleichbar zum _ENABLE_ Signal
- Stellt sicher, dass maximal eine einzelne Zeile im Speicherfeld gelesen/geschrieben wird
- Eine Wordline entspricht einer eindeutigen Adresse
- Maximal eine Wordline kann HIGH (also $1$) sein

![[Screenshot 2026-01-24 at 10.57.10.png]]

## Bitzellen

- Eine Bitzelle speichert einen Bit
- Wenn Wordline $= 1$ und Bitline $= Z$, dann wird der Wert aus der Bitzelle auf die Bitline geschrieben
- Sonst, wenn Wordline $= 1$ und Bitline $= 0$ oder Bitline $= 1$, wird der Wert der Bitline in die Bitzelle geschrieben

![[Screenshot 2026-01-24 at 11.01.24.png]]

- Es gibt verschiedene [[Speicherarten]], mit denen Bitzellen Werte speichern können
