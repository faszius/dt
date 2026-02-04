---
tags:
  - foliensatz/13
  - "#MoC"
  - cleaned
---

Bis jetzt haben wir immer nur ganze Zahlen im Binärsystem dargestellt. Jetzt wollen wir jedoch auch Kommazahlen im Binärsystem darstellen. Allgemein gibt es dafür zwei verschiedene Ansätze:

## Festkommazahlen

- Position des Kommas bleibt konstant
- Beispiel: Dezimalsystem: 3 Vorkomma- und 2 Nachkommastellen
- Kosten von 274.24€ 
- Lösung: Stattdessen als 27424 Cent repräsentieren 
- 274.24€= 27424€·10−2, allgemein $n \cdot 2^{- \ell}$ 
- Zahl “wie ohne Komma” speichern, aber letzte $\ell$ Stellen als Nachkommastellen interpretieren (speichere 27424) 
- Zusätzliche Nachkommastellen werden abgeschnitten (evtl. runden)
- Addition wie bei Ganzzahlen 
- Bei Multiplikation ergeben sich $2 \ell$ Nachkommastellen $\Rightarrow$ Runden!

## Gleitkommazahlen

- Position des Kommas kann wandern
- Angabe der Position des Kommas in Exponentenschreibweise
- Anforderung: geringer relativer Rundungsfehler
- Lösung: wissenschaftliche Notation, z.B. $2.7424 \cdot 10^2$
- Komma ist stets rechts der höchstwertigen Stelle $\neq 0$
- Speichere Mantisse $2.7424$ _und_ Exponenten $2$ (und Vorzeichen)
- Zu viele Nachkommastellen in Mantisse abschneiden (evtl. runden)

## Systeme

Diese beiden Varianten können wir mithilfe folgender beiden Systeme umsetzen:
- [[Vorzeichenloses Stellenwertsystem mit Nachkommastellen]]
- [[IEEE 754]]

