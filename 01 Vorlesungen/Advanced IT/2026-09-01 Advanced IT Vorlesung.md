---
Dozent: Pagnia
tags:
- vorlesung
---
# Threading

**Virtual Threads**: User Level Threads in Java

**Thread Pool**: Ansammlung an Threads, bsp: WorkerThread pool
- Man kann die Anzahl der Threads im Pool variieren
- Ganz viele Threads => Langsam, weil Threadmanagement und Threads die um Prozessorzeit kämpfen
- Zu wenig Threads => Langsam, weil man nicht so viel Nebenläufig machen kann

**Hauptspeicher sparen**: Threads nutzen Hauptspeicher 
- Knapper Hauptspeicher => Langsam, da Daten geswappt werden müssen

# Speicherbasierte Synchronisationsfehler

**Thread counter problem**: Man will die Threads zählen durch einen Counter im Thread
- Falls 2 gleichzeitig den Counter erhöhen/reduzieren kann es passieren, dass nur einer durchkomt => falscher Wert

**Betriebsmittel**: Etwas was man im Programm nutzt, zb E/A Gerät oder Datenstruktur

## Synchronisationsprobleme

**Betriebsmittelverwaltung**: Threads und Prozesse nutzen eine Begrenzte Anzahl von Betriebsmitteln
- Problem: Falls alle belegt sind, müssen die anderen Threads warten

**Erzeuger-Verbraucher-Problem**: Verbraucher-Threads brauchen Input von Erzeuger-Threads
- Ist der Erzeuger-Thread nicht fertig muss der Verbraucher-Thread warten

**Leser-Schreiber-Problem**: Lesende und Schreibende Threads greifen auf dieselben Daten zu
- Problem: Leser liest daten die gerade vom schreiber verändert werden => inkonsistenz
- => nur leser dürfen nebenläufig zugreifen

## Begriffe

**Kritische Daten**: Daten die nebenläufig verwendet werden
- gefährdet nebenläufige Zugriffe

**Kritischer Abschnitt**: code Abschnitt in welchem auf Kritische Daten zugegriffen wird

**Deadlock**: Verklemmung => Mehrere Prozesse, die Wechselseitig aufeinander Warten
- Programm steht, da alles aufeinander wartet => zyklische Wartesituation

**Lösungsidee Deadlock**:
- Deadlocks vermeiden auf jeden fall
- Erkennen von Deadlocks durch **Wartegraphen**
- Deadlock erkannt: einen der wartenden Threads abbrechen: andere können danach weiterlaufen, Thread kann danach neugestartet werden

## Wartegraphen
- Prozesse/Thread als Kreis
- Betriebsmittel als Rechteck
- Pfeile für Belegung/Warten

Betriebsmittel -> Prozess <=> Prozess belegt Betriebsmittel
Prozess -> Betriebsmittel <=> Prozess wartet auf Betriebsmittel

## Bedingungen fürs Auftreten für Deadlocks
- B1 **Exklusivität**: Min 2 Betriebsmittel dürfen nur 1 mal zur zeit verwendet werden
- B2**Nachforderung**: prozesse können Betriebsmittel im nachhinein belegen, auch wenn sie schon Betriebsmittel haben
- B3 **Nichtentziehbarkeit**: Betriebsmitteln können den Prozessen nicht entzogen werden

**Deadlocks treten auf wenn**:
- B4: Zyklisches Warten

## Verhinderung von Deadlocks
**Möglichkeiten**: 
- Eine der Vorraussetzungen B1, B2, B3 wird ausgeschlossen
- Betriebsmittelverteilung, sodass B4 ausgeschlossen werden kann

**Statistische Zuteilung - Two-Phase-Locking**: B2 aufgehoben, da prozesse im vorhinein betriebsmittel belegen müssen
- Prozesse müssen Betriebsmittelbedarf im vorraus melden
- Prozesse locken ein Betriebsmittel sobald sie es nutzen
- Prozesse dürfen nur los wenn alle Betriebsmittel frei sind

**dynamische Zuteilung:** B2 aufgehoben, da jede Laufphase wie ein auftrag ist siehe statistische Zuteilung
- Aufträge werden in Laufphasen unterteilt
- Es erfolgt eine statistische Zuteilung der Betriebsmittel für jede Laufphase
- Am ende der Laufphase wird alles freigegeben

**ressource Ordering**: B2 wird eingeschränkt, sodass B4 nicht eintreten kann
- Man gibt Betriebsmitteln prioritäten zuordnung: Prozesse dürfen nicht zugreifen auf Betriebsmittel mit niederigerer Priorität als die Betriebsmittel, die er bereits nutzt


**Spooling**: B1 wird aufgehoben, da ressourcen immer nur 1 mal zur Zeit verwendet werden dürfen
- Ein Server-prozess nimmt aufträge so entgegen, dass eine Ressource nur 1 mal belegt werden kann
- **sukzessiv**: nacheinander

## Bankers Algorithmus
**Annahmen**:
- Man hat $k$ gleichartige Betriebsmittel
- Prozesse geben maximalanforderung
- Prozesse fordern nur so viel nach wie sie als maximalanforderung angegeben haben
- Sukzessiv erhalten die Threads ihre Nachforderung

**Zustände**:
- sicher: Es gibt min eine Möglichkeit für eine Reihenfolge, bei der keine Deadlock auftreten kann
- unsicher: Es gibt keine Möglichkeit, Deadlock ist **möglich**

## Algemeimer Bankers Algorithmus
**Annahmen**:
- Vektor Exist: Anzahl gleichartiger Ressourcen
- Vektor Avail: Anzahl Resourcen die nicht belegt also available sind
- Matrix assigned($p_i$): Zuteilung belegte Ressourcen durch Prozesse
- Matrix needed($p_i$): Zuteilung benötigte Ressourcen von Prozessen

Man findet immer eine Reihenfolge, sobald man einen Prozess durchlaufen hat und sofern eine mögliche Reihenfolge vorhanden ist!

Lösungsstrategien:
![[Screenshot 2026-09-01 at 10.53.12.png]]

# Labor aufgabe
**Dinge von denen die Laufzeit abhängt**:
- Menge an Threads => Thread Overhead durch Scheduling und Terminierung
- Cache fülle => Wenn die Caches mit invaliden Daten gefüllt sind: länger, Mit weiter verwendeten Daten: kürzer
- Arbeitsspeicherplatz => swapping lindert performance
- CPU Kerne anzahl & prozessmenge => parallellisierungsmenge der Threads auf Kernen, prozesse die sich in die Quere kommen
- MegaHertz der RAM => Wie schnell kann man auf Arbeitsspeicher zugreifen
