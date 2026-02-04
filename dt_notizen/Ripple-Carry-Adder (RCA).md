---
tags:
  - foliensatz/07
  - cleaned
aliases:
  - RCA
  - Ripple-Carry-Adder
  - Ripple-Carry Adder
  - Ripple Carry Adder
Related:
  - "[[Conditional Sum Adder (CSA)]]"
---

## Ripple-Carry-Adder (RCA)

Aus einer Reihe an [[Addierer|Volladdierern]] können wir nun also längere Binärzahlen addieren, indem wir sie aneinander hängen. Das sieht dann wie folgt aus:

![[Pasted image 20251128135816.png]]

- Die Überträge werden über eine Kette von 1 bit Volladdierern vom LSB zum MSB weitergegeben
- Problem: der lange kritische Pfad steigt linear mit Bitbreite

## Rekursiver Aufbau des RCAs

- Wir können den RCA in ein unteres (Low) und oberes (High) Halbwort aufteilen ("Divide and Conquer")
- Der zweite Addierer muss dann auf den Übertrag aus dem ersten Addierer "warten"
- Die kritischen Pfade der beiden Teiladdierer werden addiert
- Für einen schnellen Addierer müssen das obere und untere Halbwort *gleichzeitig* bearbeitet werden
- Siehe [[Conditional Sum Adder (CSA)]]

![[Pasted image 20251203182220.png]]

