---
Dozent: Hubert
Modul: Statistik
tags:
- Vorlesung
---
# Kapitel 1 Grundlagen & Grundbegriffe

## Statistik
- **Statistik**: Methoden der Erhebung, Aufbereitung und **Analyse** von Daten
	- **Primärstatistik**: Ich erhebe die Daten selbst
	- **Sekundärstatistik**: Ich schaue bereits vorhandene Daten an

**Deskriptive Statistik**: Ich habe Daten und möchte etwas daraus ermitteln. Bsp: Ich schau mir den Kurs an und beschreibe einzelne Phänomene wie die durchschnittliche Größe
- Vollerhebung => ich habe alle Daten und kann sichere Aussagen treffen

**Induktive Statistik**: Ich ermittle aus einem teil der Daten und schließe damit auf den rest. Bsp: Ich nehme nur einen Teil des Kurses und erschließe damit die durchschnittliche Größe des gesamten Kurses
- Stichprobenerhebung => Ich nehme einen Teil der Daten und kann aussagen basierend auf der Wahrscheinlichkeitsrechnung treffen
- Kriterium für repräsentative Stichprobe => Zufallsauswahl aus der gesamten Datenmenge

## Aufgaben der Statistik 
- **Datenaufbereitung**: Kann ich mit den Daten etwas anfangen?
- **Datenanalyse**: Ermittlung von Kennzahlen anhand der Daten
- **Ergebnisinterpretation**: Ich interpretiere die Kennzahlen

## Grundbegriffe
- **Statistische Einheit/Merkmalsträger**: Das woran gemessen wird: zb. Studenten, Flaschen
- **Statistische Masse/Grundgesamtheit**: Alle Merkmalsträger
- **Stichprobe/Teilgesamtheit**: Nur ein teil der Merkmalsträger

### Merkmale 
Merkmale sind messbare Einheiten eines Merkmalsträgers

- **Qualitativ**: kategorische Einordnung, bsp. Haarfarbe, Geschlecht
- **Quantitativ**: Reele Kennzahl, bsp. Größe, Alter
	- **diskret**: nur bestimmte Werte, bsp. Anzahl Kinder
	- **stetig**: alle Werte in einem Intervall, bsp. Alter
	- **quasi-stetig**: nicht ganz wissenschaftlich, theoretisch diskret aber praktisch stetig, bsp. Körpergröße 
- **Klassenbildung**: Aufteilung quantitativer Werte in Gruppen, bsp. 1,50 - 1,60 Körpergröße
	- Idealfall => konsistente Breite, geschlossene Klassen wegen Klassenmitte

### Skalierung
Skalierung ist die Aufstellung der erhobenen Daten

- **Nominal**: Nur Verschiedenartigkeit, keine Rangordnung => immer qualitatives Merkmal, bsp. geschlecht
- **Ordinal**: Rangordnung, keine quantifizierbaren Abstände, bsp. Noten 
	=> 100% = 1.0, 50% = 4.0, 0% = 5.0 => Abstände sind nicht richtig einzuschätzen 
	=> Je nach Kontext qualitativ oder quantitativ, Bewertungsskalen
- **Kardinal**: Rangordung und Abstand, bsp. Körpergröße => immer quantitatives Merkmal

Beispiele: Skript S. 6 - 8

## Mathematische Datenanalyse

$i$: Index der Kategorie  
$f_i$: Absolute Häufigkeit  
$p_i$: Relative Häufigkeit  
$F_i$: Empirische Verteilungsfunktion  
$c_i$: Klassenbreite  

**Formeln:**

Relative Häufigkeit:
$$p_i = \frac{f_i}{n}$$

Empirische Verteilungsfunktion (nur ab Ordinale Skalierung):
$$F_i = \sum_{j=1}^{i} p_j$$

Klassenbildung mit Faustformel (Falls viele Merkmalsausprägungen):
$$k = 1 + 3{,}3129 \cdot \log_{10}(n)$$

Normierte relative Häufigkeit:
$$p_i^* = \frac{p_i}{c_i}$$

## Lageparameter
Welche Lagerparameter gewählt werden hängt von der **Skalierung** und dem **Kontext** ab

### Mittel

**Arithmetisches Mittel**: Durchschnittswert

$x_i$: Merkmal des i-ten Merkmalträgers
$$\bar{X} = \frac{1}{n} \cdot \sum x_i$$

**Gewogenes arithmetisches Mittel**: Durchschnittswert aus Klassen, falls keine tatsächlichen Werte vorhanden. Jedoch existiert hier der Informationsverlust durch die Klassen

$x_i^*$: Klassenmitte der i-ten Klasse
$$\bar{X} = \frac{1}{n} · \sum x_i^* · f_i = \sum x_i^* · p_i $$

**Geometrisches Mittel**:  Bei Wachstums durchschnitten darf **nicht** das arithmetische Mittel verwendet werden ->  [[Beispiel Geometrisches Mittel Unternehmensgewinn]]

$$x_i = 1 + \frac{\text{relative Änderung in \%}}{100}$$
$$\bar{G} = \sqrt[n]{\prod_{i=1}^{n} x_i}$$

### Median

**Median**: Mittlerer Wert aus allen Daten => **Zentralwert**
- Daten müssen sortiert sein
- Ungerade Datenanzahl: Mittlerer Wert 
- Gerade Datenanzahl: Durchschnitt der mittleren beiden Werten

=> [[Beispiel Median Monatsgelder]]

**Median bei Klassen**: Diejenige Klasse bei welcher $F_i$:  50% erreicht

$z$: Zentral-Index
$x_z^l$: Unterer Wert der Zentralklasse
$c_z$: Zentralklassenbreite

$$Z = x_z^l + c_z · \frac{0,5 - F_{z-1}}{p_z}$$

=> [[Beispiel Median Monatsgelder]]

**Quartile**: Wie Median mit 4 Sektionen
**Dezile**: Wie Median mit 10 Sektionen
**Perzentile**: Wie Median mit 100 Sektionen

### Modus

**Modus**: häufigster Wert im Datensatz bsp. häufigste Frisur

**Modus bei Klassen**: Klasse, die am häufigsten auftritt

$m$: Median-Index
$c_m$: Medianklassenbreite

$$M = x_m^l + c_m · \frac{p_m - p_{m - 1}}{(p_m - p_{m-1}) + (p_m-p_{m+1})}$$

## Fechernsche Lagerverteilung
Aussage über Verteilung => [[Beispiel Lagerparameter Nettostundenverdienste]]

$X = Z = M$: symmetrisch
$X > Z > M$: Linkssteil 
$X < Z < M$: Rechtssteil

# Aufgabe Todo
- [ ] #task 📅 2026-09-07 Aufgaben 1 - 8 Übungsskript Statistik
	- [ ] Aufgabe 1
	- [ ] Aufgabe 2
	- [ ] Aufgabe 3
	- [ ] Aufgabe 4
	- [ ] Aufgabe 5
	- [ ] Aufgabe 6
	- [ ] Aufgabe 7
	- [ ] Aufgabe 8