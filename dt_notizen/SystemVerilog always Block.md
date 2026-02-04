---
tags:
  - foliensatz/09
  - cleaned
---
- `always` führt den nachfolgenden Block in einer Endlosschleife aus
- Alle `always` Blöcke werden parallel (nebenläufig/gleichzeitig) ausgeführt

![[Pasted image 20251210114817.png]]

![[Pasted image 20251210114827.png]]

## Warten auf Ereignisse

Häufig wollen wir etwas nur berechnen, wenn ein bestimmtes Ereignis auftritt, z.B. eine steigende Taktflanke
- `@ <expr>` wartet auf eine Änderung des kombinatorischen Ausdrucks `<expr>`
- `@(posedge <expr>)` wartet auf eine steigende Flanke von `<expr>`
  ($0 \rightarrow 1$)
- `@(negedge <expr>)` wartet auf eine fallende Flanke von `<expr>`
  ($1 \rightarrow 0$)
- `@(<event1>, <event2>)` wartet auf das Eintreten eines der aufgelisteten Ereignisse
	- Wird auch als Sensitivitätsliste bezeichnet
- `@*` wartet auf Änderung eines der im `always` Block gelesenen Signale

### Beispiele

Dieser Code:
![[Pasted image 20251210115411.png]]

Führt zu folgendem Timing-Diagramm:
![[Pasted image 20251210115426.png]]

## Spezialisierte `always` Blöcke

Um [[SystemVerilog Speicherelemente]] umzusetzen

- `always`
	- Prozess, wird endlos oder durch Ereignis (z.B. `@(CLK)`) getriggert ausgeführt
- `always_comb`
	- Funktioniert (ähnlich) wie `always @*`
	- Wird für synchrone Schaltungen kaum benutzt
- `always_ff @(<event>)`
	- Funktioniert (ähnlich) wie `always @(<event>)`
	- Gedacht für sequentielle Logik mit Flip-Flops
- Spezialisierte Blöcke benutzen, damit Synthese-Tools die Absicht des Designs besser verstehen und auf Fehler hinweisen können