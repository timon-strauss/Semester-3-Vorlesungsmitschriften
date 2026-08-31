---
Dozent: Pagnia
tags:
- Vorlesung
---
# Nebenläufigkeit
**Programm**: Folge von Maschinenbefehlen, die auf dem Prozessor ausführbar sind (passiv)

**Prozess**: stellt Ausführungsumgebung für Programme

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

**User Level Threads** => Kernel kennt nur Prozesse, keine Threads
	- Threads realisiert durch Sprachbibliotheken oder eigen implementation
	- **asynchrone E/A** => Auslagerung des Wartens auf Eingabe auf Thread, Prozess kann weiterlaufen => Thread wartet auf Eingabe, rest arbeitet weiter: Interupt sobald Thread die Eingabe abgearbeitet hat
	- Eigene Scheduling Strategie
**Kernel Level Threads** => Threads sind im Kernel bekannt und auf Prozesse gemappt
	- Threads können auf Prozessorkerne aufgeteilt werden => User Level nur Prozesse
	- Bei UL blocken Threads bei zb Seitenfehlern den kompletten Prozess, bei KL kann der Prozess weiterlaufen
	- Thread funktionen sind alles System calls
	- System calls sind teuer => threads recyceln: Threads nicht beenden sonder wiederverwenden