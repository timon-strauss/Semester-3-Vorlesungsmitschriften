---
Dozent: Pagnia
tags:
- vorlesung
---
# Aufgabe 10

![[Übung Advanced IT Aufgabe 10]]

# Synchronisationsbedingungen

**Gegenseitiger Auschluss**: Kritische Abschnitte dürfen nur exklusiv von einem Thread zu gleichen Zeit ausgeführt werden

**Reihenfolge**: Kritische Abschnitte dürfen nur in einer bestimmten Reihenfolge ausgeführt werden => zb. Daten müssen erst geschrieben und dann verändert werden

## Synchronisationsgraph

**Einseitiger Auschluss**: Wenn A sich in Ausführung befindet darf B nicht ausführen im kritischen Abschnitt

**gegenseitiger Ausschluss**: Nur alternierende Ausführung von kritischen Abschnitten
- Wie stellt man das dar: Pfeile von A -> B und B -> A

**Reigenfolge**:
- Bedingung: $Anf(A) <= End(A) + k$
- Für k = 0 => Für jedes B muss min. 1 A durchgelaufen sein => AB, AAB, AABB
- Für k = 1 => K puffert 1 Ausführung von B, danach wieder für B muss min. 1 A durchgelaufen sein => BA, AB, ABB, BAA
- => k puffert ausführungen von B 
- Wichtig: B darf ausgeführt werden sobald A durchgelaufen sind, dh. man kann A und B synchron laufen lassen, sofern A davor einmal durchgelaufen ist.

**geschachtelte kritische Abschnitte**: Kritischer Abschnitt in B liegt in A
- Beispiel: Anmeldung => Ich muss vorher angemeldet sein, bevor ich etwas ausführen darf in einer App

## Basismechanismen - Wie kann man Synchronisation im Kernel umsetzen
**Round-Robin:** Nach Ablauf der Scheibe wird ein Hardware-Interrupt ausgeführt => Prozesswechsel
- Bei kritischen Abschnitten werden Interrupts gepuffert
- Thread bleibt solange in running bis die Interrupts wieder angestellt werden => kritischer Abschnitt ist vollständig durchlaufen
- Problem: Thread blockiert alle Interrupts, zb Tastatur usw wird hinten angestellt
- Auf Multiprozessorsystemen nicht genug, nur bei Einprozessorsystemen möglich
- Systemcall notwendig, da Interrupts nur im priviligierten modus ausgestellt werden können

**atomar**: Wert vorher und Wert nachher => keine Zwischenzustände

**Atomare Speicheroperationen**: 
- Hardware entscheidet bei konflikten wer gewinnt
- Hardware befehle => Ich führe Befehle in einem atomaren Block aus
- TSL: Erster Thread setzt globale variable auf 1, alle folgenden werden in einer Schleife gehalten, solange diese besetzt ist
- Problem: Threads, die nicht in den kritischen Bereich sollen, laufen die schleife und blockieren den prozessor
- Problem: Round Robin nimmt den Thread raus der TSL blockiert => Alle warten auf etwas was nicht ausführt, prozessor wird unnötig blockiert
- Problem: Nachdem TSL unblockiert wird ist es zufällig welcher Thread als nächstes kommt

**Semaphoren**: Methoden `p` und `v`
- Thread will kritischen Abschnitt betreten => muss p ausführen
- Startwert 1 => 
	1. Thread1 ruft p auf: ctr = 0, Thread1 läuft
	2. Thread2 ruft p auf: ctr = -1, Thread2 wartet
	3. Thread3 ruft p auf ctr = -2, Thread3 wartet
	4. Thread1 ist fertig, ruft v auf => ctr = -1, Thread 1 ist durch, Thread2 wird gestartet
	5. usw.
- => Startwert definiert wieviele Threads gleichzeitig den kritischen Abschnitt durchlaufen dürfen

**Semaphore in Java**:
- nutzt *NICHT* TSL
- acquire() setzt Threads, die nicht laufen sollen in Zustand:`blockt`
- Diese landen in einer Waiting FIFO warteschlange
- führt ein aktiver Thread release() aus, wird der erste aus der Waiting Warteschlange in `ready` versetzt
- System call "weckt den Thread auf", kein Interrupt nötig