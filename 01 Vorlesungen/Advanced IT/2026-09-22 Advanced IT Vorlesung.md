---
Dozent: Pagnia
Skript: S. 65 - 81
tags:
- vorlesung
---

# Erzeuger Verbraucher Problem

**Problem**: 
- Verbraucher muss warten bis erzeuger erzeugt hat 
- Erzeuger muss warten bis Verbraucher verbraucht hat

**Ring-Puffer**: 
- Daten werden in den Puffer gelegt
- hinten voll => Vorne wieder reinlegen
- Kreisförmige Datenablage => Ring
- => Daten können nacheinander aus dem Puffer entnommen werden
- Puffer voll => Erzeuger wartet
- Puffer leer => Verbraucher wartet

![[Übung Advanced IT Ring Buffer]]

## Allgemeines Erzeuger Verbraucher Problem
Mehrere Verbraucher und Mehrere Erzeuger:

![[Screenshot 2026-09-22 at 11.03.11.png]]

# Betriebsmittelverwaltungs Problem

**Problem**: n Drucker und m Threads => Wie können wir gegenseitigen Ausschluss gewährleisten und trotzdem alle Drucker vollständig auslasten

**Semaphore-Lösung**: Drucker werden als Semaphore ausgedrückt mit der Anzahl n als Startwert
- n Threads werden auf Drucker verteilt
- weitere Threads müssen warten bis ein anderer v() ausführt und daher einen drucker freigibt

# Leser Schreiber Problem

R: Read
W: Write
- Parallelles Lesen ist unkritisch
- Parallelles Schreiben nicht zugelassen
- Lesen und Schreiben nicht gleichzeitig

![[Screenshot 2026-09-22 at 11.12.41.png]]