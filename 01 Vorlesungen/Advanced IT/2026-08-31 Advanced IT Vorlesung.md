---
Dozent: Pagnia
tags:
- Vorlesung
---
# Nebenläufigkeit
**Programm**: Folge von Maschinenbefehlen, die auf dem Prozessor ausführbar sind (passiv)

**Prozess**: stellt Ausführungsumgebung für Programme
- Schutzumgebung => Prozesse beeinflussen sich nicht gegenseitig direkt
- Eigener Adressraum

**Multi-Processing System**: kann mehrere Prozesse zeitgleich laden
- Adressräume müssen vollständig abgetrennt sein, sonst gibt es probleme
- OS trennt die Adressräume, schnittstelle => System Calls

**Time-sharing System**: kann mehrere Prozesse scheinbar zeitglich durch Nebenläufigkeit ausführen
- Prozessor-Multiplex: Mehrere Kerne die als Baustein vereinigt sind
- OS übernimmt die Verteilung der Berechnungen der Prozesse

**Nebenläufigkeit**: Prozesse werden in kurzen Intervallen alternierend ausgeführt

**Prozess Zustände**:
- Ready: bereit zur ausführung
- Blockt: Warten auf ein Ereignis
- Running: Prozess wird ausgeführt

**Synchrone E/A**: Prozess wartet auf Eingabe und kann deswegen nicht weiterlaufen bis dei Eingabe kommt

**NOP**: No Operations => Wenn Computer nichts machen soll wird NOP wiederholt ausgeführt. CPU darf nicht still stehen

> ## Sequenzieller Server
Ein Prozess arbeitet einzelnd die Aufträge ab => niedriger Durchsatz
=> Ein Prozess bedeutet, dass auch nur ein Prozessor genutzt wird
Besser: Multi-processing => Mehrere Prozesse arbeiten nebenläufig die Anfragen ab

**Scheduling:**

**round-robin**: Zeitscheiben => Prozess hat X zeit zum abarbeiten:
	- Prozess blockt: Prozess hat fertig gerechnet und wartet auf nächste eingabe
	- Prozess running: Am Ende wieder in Ready, da er nur auf das nächste Berechnungsfenster wartet

Wann Prozesswechsel:
- Zeitscheibe ist durch
- Aktiver Prozess ist blockt oder terminated

**Seitenfehler**: Zugreifen auf geswappte Daten eines Prozesses
- Seitenfehler erzwingen einen Prozesswechsel, da das geswappte erst geladen werden muss. Prozess geht erstmal in blockt

## Prozesszustandswechsel
Scheduler entscheidet welcher Prozess in running sich befinden darf.
=> Ready -> running (Scheduler führt prozess aus)
=> Running -> Ready (Prozess ist noch nicht fertig wird aber vom Scheduler rausgenommen)
=> Running -> blockt (Prozess wartet auf input)
=> Blockt -> Ready (Input ist angekommen)

**Cache Invalidierung**: Gecachte Daten des Prozesses werden beim Wechsel aus Running rausgeschmissen

## Threading
Ich will in meiner Anwendung nebenläufigkeit realisieren

Mehrere Prozesse innerhalb der selben Anwendung
- Zeitaufwand bei Adressraumwechsel
- Gecachte Daten im Hardware cache müssen invalidiert werden => Cache hat noch Daten die aus dem vorherigen Adressraum sind und muss die rauswerfen
- geteilte Daten können nur über Systemcalls abgerufen werden => OS Kontextwechsel
- => Prozesse sind vergleichsweise langsam

**Thread**: Thread of Execution: Kontrollfluss der Ausführung => Nebenläufigkeit innerhalb eines Prozesses
- Geteilter Adressraum und Daten
- => kein Schutzraum
- keine Hardware Cache invaldierung
- keine systemcalls, da kein Adressraumwechsel

**was gehört dazu**: kleinstmöglicher Prozess
- Zustand (Wie bei Prozessen)
- Programm-Counter => Adresszähler 
- Stack => Speichert Rücksprunge (Verschachtelungen), Funktionslokal daten
- Register

`&` => Pointer: es wird nur die Adresse übertragen

### User Level Threads
 Kernel kennt nur Prozesse, keine Threads

**Vorteile**:
- Effizienter: Keine Systemcalls, da wir im Prozess wechseln und nicht auf dem Kern selbst
- Flexibilität: Kernel kennt Threads nicht => ich kann selbst meine Scheduling Strategie wählen
- Skalierbarkeit: Threads verbrauchen keine Speicherressourcen => ich kann ganz viele machen

**Nachteile**:
- Blockierung: Wartet ein Thread auf Daten (E/A) blockiert der gesamte Prozess (synchrone E/A)
- => Lösung dafür: **Asynchrone E/A** => Prozess stößt E/A an, switcht intern den Thread und läuft weiter. Prozess wartet nicht auf E/A sondern nimmt nur entgegen, damit der Thread weitermachen kann. Dafür wird nicht der normale Systemcall für E/A aufgerufen, sondern eine non blocking Anfrage
- Keine Parallellität: Prozess kann Threads nicht auf Kerne verteilen, da der Kernel diese nicht kennt

### Kernel Level Threads
Threads sind im Kernel bekannt und auf Prozesse gemappt

**Vorteile**:
- Parallellität: Threads können auf kerne verteilt werden
- Keine Blockierung: geblockte Threads blockieren nicht den Prozess

**Nachteil**:
- Nicht jeder Kernel implementiert KL Threads
- System call overhead: Kontextwechsel, da bei Prozesswechsel der Kontext geladen wird
	- System calls sind teuer => threads recyceln: Threads nicht beenden sonder wiederverwenden
- Ressourcenverbrauch: Threads müssen im kernel gespeichert sein
- Scheduling: OS definiert scheduling