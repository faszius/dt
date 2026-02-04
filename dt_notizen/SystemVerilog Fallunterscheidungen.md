---
tags:
  - foliensatz/07
  - cleaned
---

## `if-else` Konstrukt

![[Pasted image 20251128192000.png]]

- `if-else` darf nur in `always_comb` (und ähnlichen Blöcken) verwendet werden

### Synthese von `if-else`

- Mehr Abstraktion, aber im Endeffekt das gleiche Ergebnis

![[Pasted image 20251128192119.png]]

## Fallunterscheidungen

### `case`

- Beispiel: Dezimale 7-Segment Anzeige

![[Pasted image 20251128192145.png]]

- `case` darf nur in `always_comb` und `always` Blöcken verwendet werden
- Für kombinatorische Logik müssen alle Eingabe-Optionen abgedeckt werden
- Explizit oder per `default` ("alle anderen")

### `casez`

![[Pasted image 20251128192328.png]]

