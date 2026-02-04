---
tags:
  - foliensatz/11
  - cleaned
---

- Ampelsteuerung: [[Endliche Zustandsautomaten|Moore]]-Automat besser geeignet, weniger explizite Transitionen notwendig, einfachere Ausgabelogik
- 101 Mustererkennung: [[Endliche Zustandsautomaten|Mealy]]-Automat besser geeignet, weniger Zustände notwendig
- Je nach Anwendungsfall kann eine der Optionen besser sein
- In der Regel:
	- Moore besser, wenn Ausgaben statisch (z.B. in aktueller Ampelphase)
	- Mealy besser, wenn Ausgaben kurzfristige Aktionen auslösen (z.B. 1 ausgeben, wenn die letzten drei gelesenen Bits 101 waren)
	- Außerdem: Mealy reagiert schneller auf Änderungen der Eingabe, siehe nächste Folien