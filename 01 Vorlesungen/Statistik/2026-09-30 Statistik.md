
---
Dozent: Hubert
Skript: S. 31
tags:
- Vorlesung
---
## Poissonverteilung
Unabhängigkeit vorrausgesetzt

Bsp. Betrieb mit 200 PCs
Erfahrungswert: pro Tag bei 2% Störungen
ZV X: Zahl der Störungen

Poissonverteilung darf angewendet werden, da p < 10% & n > 50

$$\lambda = n · p = 200 · 0,2 = 4$$
$$P(X = 2) = \frac{\lambda^k}{k!} · e^{-\lambda} = \frac{4^2}{4!} · e^{-2} = 14,65\%$$
$$E(X) = \lambda = 4\ PCs$$
$$Var(X) = \lambda = 4 => \sigma = \sqrt{4} = 2\ PCs$$

 Mit Binomialverteilung

$$P(X = 2) = \binom{200}{2} · 0,02^2 · 0,98^198 = 0,1458 => 14,58\%$$
$$E(X) = 200 · 0,02 = 4\ PCs$$
$$Var(X) = 200 · 0,02 · 0,98 = 4 => \sigma = \sqrt{4} = 2\ PCs$$

Hier unterscheidet es sich zur Poissonverteilung, da n · p · q. Jedoch ist bei der approximation q nah genug an 1 dran, sodass es nicht ausschlaggebend wird.

**Poisson muss teilweise angewendet werden**

Bsp. KFZ-Versicherung
ZV X: Anzahl der Verkehrsunfälle mit Schaden > 100.000€ an einem Tag
langjähriger Erfahrungswert: 3 solcher Unfälle pro Tag
unabhängig voneinander

$E(X) = 3 = n · p · q$ => man kann hier mit der Binomialverteilung p nicht ermitteln! => Poissonverteilung

$$E(X) = 3 = \lambda$$
$$P(X = 0) = \frac{3^0}{0!} · e^{-3} = 0,0498 => 4,98\%$$

## Fazit - diskrete Verteilungen

1. Hypergeometrische Verteilung -> keine Unabhängigkeit (Urne: Ziehen ohne Zurücklegen)
	für $\frac{n}{N} <= 0,05$ : Approximierung durch Binomialverteilung
2. Binomialverteilung -> Unabhängigkeit (Urne: Ziehen mit Zurücklegen)
	für n >= 50 und p <= 0,1 : Approximierung durch Poissonverteilung möglich
3. Poissonverteilung -> n groß, p klein 
	Anwendbar wenn nur $E(X) = \lambda$ vorliegt

## Stetige Zufallsvariablen

**Symmetrieeigenschenschaft**: links und rechts vom Erwartungswert => 50%

**Standardabweichung**: Wendepunkt der Glockenkurve

![[IMG_2972 1.png]]

**Zentraler Grenzwertsatz**: Summe von unabhängigen und identisch verteilten Zufallsvariablen konvergiert bei steigenden n gegen eine Normalverteilung. Diskrete Werte konvergieren zu stetigen 

bsp. Würfel 2x Werfen

|$\sum$|$\bar{X}$|Wahrscheinlichkeit|
|-|-|-|
|2|1|$\frac{1}{36}$
|3|1,5|$\frac{2}{36}$
|4|2|$\frac{3}{36}$
|5|2,5|$\frac{4}{36}$
|..|..|..|
|12|6|$\frac{1}{36}$

bsp. Holbearbeitungsmaschine zur Herstellung von Brettern
ZV X: dicke eines Bretts
$$\mu = 1,2\ cm,\ \sigma = 0,04\ cm$$

$P(X =< 1,12)$?

$$Z = \frac{1,12 - 1,2}{0,04} = -2$$
Tabelle Nachschauen => Anhang
=> $P(X =< 1,12) = P(Z =< -2) = 0,0228 => 2,28\%$

Einzelwahrscheinlichkeit, da Fläche nicht vorhanden
$$P(X = 1,12) = 0$$

Da Einzelwahrscheinlichkeit = 0 ergibt sich:
$$P(1,18 <= X) = P(1,18 < X)$$

Fall:
$$P(1,18 <= X <= 1,26) = P(x <= 1,26) - P(1,18 <= X)$$

Fall:
$$P(X < 1,3044) = 1 - P(X => 1,3044)$$

Mathematische Eleganz ohne Nebenrechnung:
$$P(x =< 1,12) = \phi(\frac{1,12 - 1,2}{0,04}) = \phi(-2) = 0,0228 => 2,28\%$$

## Verständnis Beispiel

Bsp. Lebensdauer von Autoreifen
$$\mu = 40.000\ km, \sigma = 5.000\ km$$

$$P(X =< 36.000) = \phi(\frac{36.000 - 40.000}{5.000}) = \phi(-4/5) = \phi(-0,8) = 0,2119 => 21,19\%$$

$$P(X > 46.000) = P(X <= 34.000) = \phi(\frac{34.000 - 40.000}{5.000}) = \phi(-1,2) = 0,1151 => 11,51\%$$

$$P(X = 38.000) = 0$$

$$P(37.000 =< x < 44.000) = \phi(\frac{44.000 - 40.000}{5.000}) - \phi(\frac{37.000 - 40.000}{5.000}) = \phi(0,8) - \phi(-0,6) = 0,7881 - 0,2743 = 0,5038$$

## Intervallrechnung

Bsp. Laufleistung von Autoreifen
n = 625 => durchschnitt X = 6.000 km
sigma bekannt mit 4.800 km
Irrtumswahrscheinlichkeit alpha = 5% => Konfidenzniveau = 95%

$$P(\bar{X} - z · \frac{\sigma}{\sqrt{n}} =< X =< \bar{X} + z · \frac{\sigma}{\sqrt{n}}) = 95\% = P(6.000 - z · \frac{4.800}{\sqrt{625}} =< X =< 6.000 + z · \frac{4.800}{\sqrt{625}})$$

Z ermitteln anhand Tabelle => 95% => 1,96

$$P(6.000 - 1,96 · \frac{4.800}{\sqrt{625}} =< X =< 6.000 + 1,96 · \frac{4.800}{\sqrt{625}}) = 95\% = P(35.623,69 =< \mu =< 36.376,32)$$

# Todo
- [x] #task Statistik 29 - 39