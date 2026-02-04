---
tags:
  - foliensatz/11
  - cleaned
---

- Die Anzahl von benötigten Submodulen hängt oft vom [[SystemVerilog für parametrisierte Module|Parameter]] ab
- Das kann mit iterativen Instanziierung bewältigt werden

![[Pasted image 20260116162627.png]]

Aufbau iterative Instanziierung:
1. [[SystemVerilog Arrays und Vektoren|Vektoren]] für Ein- und Ausgabe der [[SystemVerilog Module|Module]] definieren
2. Schleifenvariable mit `genvar` definieren
3. `generate`-Block schreiben
	1. In den `generate`-Block eine for-Schleife mit `N` Wiederholungen packen
	2. In der for-Schleife das Modul instanziieren. Jedes Modul sollte auf verschiedene Bereiche der Eingabevektoren zugreifen, und auf verschiedene Bereiche der Eingabevektoren schreiben (das erreicht man, in dem man die Schleifenvariable benutzt). Keine zwei Module sollten auf den gleichen Bereich im Ausgabevektor schreiben! Was aber gerne gemacht wird ist dass ein Modul auf ein Bereich im Ausgabevektor schreibt, welches dann vom nächsten Modul gelesen wird (wie in dem Beispiel)

## Implementierung eines 4-bit Zählers

![[Pasted image 20260116163428.png]]

![[Pasted image 20260116163442.png]]

## Weitere Anwendungen für iterative Instanziierung

### Schieberegister

- Bei jeder steigenden Taktflanke wird der Speicherinhalt ein Flip-Flop weiter verschoben (FIFO-Prinzip: First In - First Out)
	- Neues Bit $S_\text{in}$ wird eingelesen
	- Letztes Bit $S_{out}$ wird nach außen verschoben/verworfen
- Seriell-Parallel-Wandler: Wandelt den seriellen Eingang ($S_\text{in}$) in den parallelen Ausgang ($Q_{0:N-1}$) um

Symbol:
![[Pasted image 20260116163708.png]]

Implementierung:
![[Pasted image 20260116163718.png]]

SystemVerilog Code:
![[Pasted image 20260116163740.png]]

### Schieberegister mit parallelem Laden

- Für $\text{Load} = 1$: normales $N$-Bit Register
- Für $\text{Load} = 0$: Schieberegister
- Kann dadurch sowohl als Seriell-Parallel-Wandler ($S_\text{in}$ zu $Q_{0:N-1}$, $\text{Load}=0$) als auch Parallel-Seriell-Wandler ($D_{0:N-1}$ zu $S_\text{out}$, $\text{Load} = 0$) fungieren

![[Pasted image 20260116164214.png]]

