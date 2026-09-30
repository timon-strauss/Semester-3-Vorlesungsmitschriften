---
Dozent: Hubert
skript: S. 24 - 30 
tags:
- vorlesung
---
# Kapitel 4 Wahrscheinlichkeitsrechnung

**Vereinigung**: bsp. Würfel

A = {gerade Zahl}
B = {ungerade Zahl}
C = {1,2,3}

$A \cup C = \{1,2,3,4,6\}$
$A \cap C = \{2\}$
$A \cap B = \varnothing$ => disjunkte Ereignisse

**klassicher Wahrscheinlichkeitsbegriff**: 
- Nur wenn alle Elementarereignisse die gleiche Wahrscheinlichkeiten haben
- Anzahl günstige Fälle / Anzahl aller Fälle

**statistischer Wahrscheinlichkeitsbegriff**: 
- Zufallsexperiment => Ganz oft probieren

**subjektiver Wahrscheinlichkeitsbegriff**: 
- Gefühlte Wahrscheinlichkeiten => Meinung

**Disjunkt**: 
$A_1 = {1,2}$
$A_2 = {3}$
$A_3 = {4,5}$

$$P(A_1 \cup A_2 \cup A_3) = P(A_1) + P(A_2) + P(A_3) = \frac{2}{6} + \frac{1}{6} + \frac{2}{6} = 1$$

**Konjunkt**:
$A = {1,2}$
$B = {1,3}$

$$P(A \cup B) = P(A) + P(B) - P(A \cap B) = \frac{2}{6} + \frac{2}{6} - \frac{1}{6} = \frac{3}{6}$$

**Bedingt**:
$A = {1,2}$
$B = {1,3}$

$$P(A/B) = \frac{P(A \cap B)}{P(B)} = \frac{\frac{1}{6}}{\frac{2}{6}} = \frac{1}{2}$$ 

**Beispiel**: Urne mit 10 Kugeln (3w , 5s, 2r) ohne zurücklegen, also ohne Unabhängigkeit:
A1 : rot im 1. Zug
A2 : weiß im 2. Zug
A3 : rot im 3. Zug

$$P(A_1 \cap A_2 \cap A_3) = \frac{2}{10} · \frac{3}{9} · \frac{1}{8} = \frac{1}{120} = 0,83 \%$$

mit zurücklegen, also Unabhängigkeit:
$$P(A_1 \cap A_2 \cap A_3) = \frac{2}{10} · \frac{3}{10} · \frac{2}{10} = \frac{12}{1000} = 1,2 \%$$

![[Beispiel Theorem der Totalen Wahrscheinlichkeit und Bayes]]

## 4.2 Kombinatorik

**Permutation**: Möglichkeiten zur Reihenbildung => $P_n = n!$

**Variation**: Ohne Wiederholung
Autorennen 15 Autos => Platz 1-3

$$V_{15}^{(3)} = \frac{15!}{(15 - 3)!} = 2730 \ Möglichkeiten$$

**Variation**: Mit Wiederholung
Zahlenschloss mit 3 Drehringen von 0 - 9

$$V_{10}^{(3)} = 10^3 = 1000 \ Möglichkeiten$$

**Kombination**: ohne Wiederholung
Lotto "6 aus 49"

$$C_{49}^{6} = \frac{49!}{6! · 43!} = 13.983.816 \ Möglichkeiten$$

**Kombination**: ohne Wiederholung
Lotto "6 aus 49" mit zurücklegen

$$C_{49}^{6} = \frac{(49 + 6 - 1)!}{6! · (6-1)} = 25.827.165 \ Möglichkeiten$$

**Erkenntnis**: Permutation ist eine Variation ohne Wiederholung mit k = n

## 4.3 Zufallsvariable und ihre Verteilung

**Zufallsvariable**: Zuordnung von Ergebnissen an eine reele Zahl

### diskrete Zufallsvariablen

**Wahrscheinlichkeitsfunktion**: Säulendiagramm

| $x_i$ | $f(x_i) = P(X = x_i)$ | F(X) |
|-|-|-|
|0|25\%|25\%| 
|1|50\%|75\%|
|2|25\%|100\%|

**Verteilungsfunktion**: Stufenförmiger Verlauf

**Erwartungswert**: $E(X) = 0 · 25\% + 1 · 50\% + 2 · 25\% = 100\%$ => Durchschnittlich 1 Wappen bei 2 mal werfen

**Varianz**: $Var(X) = (0 - 1)^2 · \frac{1}{4} + (1 - 1)^2 · \frac{2}{4} + ... = 50\%$
=> Standartvarianz: $sigma = \sqrt{0,5} = 0,71 \ Wappen$
=> Wenn ich hinreichend oft genug das Experiment durchführe, habe ich durchschnittlich 1 Wappen pro experiment mit einer Streuung von 0,71 Wapen

### stetige Zufallsvariable

Die Wahrscheinlichkeit für genau ein X = x geht gegen 0, da unendlich viele Möglichkeiten
=> Flächenberechnung für einen Bereich => Dichtefunktion

**Verteilungsfunktion**: Start am Anfang => Fläche bis zu dem Punkt

## 4.4 Wahrscheinlichkeitsverteilungen

### Diskrete Zufallsvariablen

**Binomialverteilung**: 
- Unabhängigkeit der Vorgänge
- Wiederholung eines Zufallsvorgangs

X : Zahl der Wappen

$$P(X=1) = \binom{3}{1} · 0,5^1 · 0,5^{3-1} = 0,375 = 37,5\%$$

$$E(X) = 3 · 0,5 = 1,5 \ Wappen$$

$$Var(X) = 3 · 0,5 · 0,5 = 0,75 => sigma = \sqrt{0,75} = 0,866\ Wappen $$

Bsp. Versandhändler
10% der Kleidungsstücke werden zurückgesendet
zufällig ausgewählter Tag mit 8 Bestellungen

zv X : Zahl der Rücksendungen

$$P(X = 2) = \binom{8}{2} · 0,1^2 · 0,9^{8-2} = 0,1488 = 14,88\%$$

$$E(X) = 8 · 0,1 = 0,8\ Rücksendungen$$

$$Var(X) = 8 · 0,1 · 0,9 = 0,72 => sigma = \sqrt{0,72} = 0,85 \ Rücksendungen$$

**Hypergeometrische verteilung**:
- keine Unabhängigkeit
- große Variable => Grundgesamtheit
- kleiner Variable => Stichprobe

Bsp. Montagebetrieb bestimmt 10(n) Steuerungseinheiten einer Gesamtproduktion von 20(N) Teilen von seinem Lieferanten. 2(M) Der 20 Teile sind defekt. ZV X : defekte Teile in Lieferung

$$P(X = 1(m)) = \frac{\binom{20 - 2}{10 - 1} · \binom{2}{1}}{\binom{20}{10}} = 52,63\%$$

Approximierung bei 5% Stichprobe => 10 Stichproben : 200 gelieferte Teile, dann darf ich die Binomialverteilung nutzen, da dann der Unterschied beim nicht zurücklegen sehr gering ist

**Unterschied**:
Bsp. Montagebetrieb bekommt 10 Steuerungseinheiten aus einer Massenproduktion. Erfahrungswert 10% der teile defekt

$$P(X = 1) = \binom{10}{1} · 0,1^1 · 0,9^9 = 0,3874 = 38,74\%$$
=> Zu 38,74 % ist 1 Teil kaputt

$$E(X) = 10 · 0,1 = 1\ defektes\ Teil$$

$$Var(X) = 10 · 0,1 · 0,9 = 0,9 => sigma = \sqrt{0,9} = 0,949\ defekte\ Teile$$ 

**Warum** ist bei der Hypergeometrischen Verteilung 1 Teil wahrscheinlicher Kaputt als bei dem Binominalfall, wenn beide gleich viele Teile untersuchen?

=> I. P(X = 0) + P(X = 1) + P(X = 2) = 1
II. P(X = 0) + P(X = 1) + .. P(X = 10) = 1

Dadurch ist der Binominalwert unbedingt kleiner