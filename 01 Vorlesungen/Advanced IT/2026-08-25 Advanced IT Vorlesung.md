---
Dozent: Pagnia
Skript: S. 1 - 13
tags:
- vorlesung
---
# Osi Schichten
- Physical => phyische Übertragung
- Data link => Fehlerkorrektur
- Network => logische Netzwerke verknüpfen
- transport => Datenübertragung durch sockets (Protokoll angabe und Port)
- session => 
- presentation =>
- application =>

# Todo
- [x] #task 📅 2026-08-31 Advanced IT Osi Schichtenmodell wiederholen

=> [[Übung Advanced IT Osi Modell]]

# Allgemeines
- POSIX => Standard schnittstelle vom OS
- System calls sind routinen die das OS abietet, um befehle auszuführen. Sie kontrollieren zb Berechtigungen
- shell => möglichkeit zur kommunikation zum OS
- Hilfsprogramme sind vorgefertigt vom OS, kapseln System calls, zb Dateiname ändern

# Shell
- interne Kommandos werden direkt ausgeführt 

# Bash
- wird mit `bash` ausgeführt
- art einer shell
- stdin / stdout => Standard ein/ausgabe
- ">>" heißt stdout ohne überschreiben
- gerätedatei dev/ für device
- bin/ heißt binaries => ausführbare standardprogramme
- $ gibt eine Ausgabe an, $1, $2 usw
- `rm -r` => rekursives löschen
- `rm -f` => forciertes löschen
- root ist der superuser
- mount => montieren von Datenträgern in den Dateibaum; umount => demontieren
- Hardlink speichert referenz auf speicher
- softlink speichert referenz auf Pfad
- ausführen mit {programmname} falls berechtigungen mit chmod u+x vorhanden sind
=> Aktuelle Bash führt programm aus
- ausführen mit bash {programmname} keine berechtigungen nötig
=> Neue Bash wird gestartet und führt das programm aus, daher keine berechtigungennötig
- programm hat `#!/bin/bash` drin => Es wird immer eine Bash gestartet die ausführt
=> sh {programmname} => shell wird gestartet => shell startet bash => bash führt programm aus

# Aufgabe 1
- | = pipe => Output links ist Input rechts

# Aufgabe 2
- echo gibt am Ende immer einen Zeilenumbruch
- Dadurch 2 lines, die jeweils durch 1 byte dargestellt werden
- wc gibt lines, words, bytes aus