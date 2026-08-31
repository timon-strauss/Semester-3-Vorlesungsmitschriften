---
Dozent: Holey
tags:
- Übung
---
# Pivot Verfahren
Aufschreiben des LGS als Matrix:

| $x_1$ | $x_2$ | $x_3$ | $b$ |
|-|-|-|-|
|2|4|-2|20 |
|1|3|-2|13|
|-1|1|1|5 |

Die Diagonal Form soll erreicht werden:

| $x_1$ | $x_2$ | $x_3$ | $b$ |
|-|-|-|-|
|1|0|0| $b_1$ |
|0|1|0|$b_2$|
|0|0|1|$b_3$ |

Hierfür wird Reihe für Reihe ein Pivot element genommen:

| $x_1$ | $x_2$ | $x_3$ | $b$ | |
|-|-|-|-|-| 
|2|4|-2|20 | Pivot Reihe |
|1: PKS|3|-2|13|
|-1: PKS|1|1|5 |
|Pivot Spalte |

Folgende Regeln werden iterativ angewant:

$I: neue\ pivot = \frac{alte\ pivot}{pivot}$
$II: neue\ Reihe = alte\ Reihe - PKS · neue\ pivot$

=> Für Beispiel:

$$I: \begin{pmatrix} 2 \\ 4 \\ -2 \end{pmatrix} · \frac{1} {2} = \begin{pmatrix} 1 \\ 2 \\ -1 \end{pmatrix}\ \&\ 20 · \frac{1}{2} = 10 $$

$$II: Reihe 2 => PKS = 1$$
$$\begin{pmatrix} 1 \\ 3 \\ -2 \end{pmatrix} - 1 · \begin{pmatrix} 1 \\ 2 \\ -1 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ -1 \end{pmatrix}\ \&\ 13 - 1 · 10 = 3$$

$$II: Reihe 3 => PKS = -1$$
$$...$$

=>

| $x_1$ | $x_2$ | $x_3$ | $b$ |
|-|-|-|-|
|1|2|-1|10 |
|0|1|-1|3|
|0|3|0|15|

Nächste Iteration:

| $x_1$ | $x_2$ | $x_3$ | $b$ | |
|-|-|-|-|-|
|1|2: PKS|-1|10 |
|0|1: Pivot|-1|3|Pivot Reihe|
|0|3: PKS|0|15|
||Pivot Spalte|

$$I\ \&\ II\ =>$$

| $x_1$ | $x_2$ | $x_3$ | $b$ |
|-|-|-|-|
|1|0|1|4 |
|0|1|-1|3|
|0|0|3|6|

$$I\ \&\ II\ =>$$

| $x_1$ | $x_2$ | $x_3$ | $b$ |
|-|-|-|-|
|1|0|0|2|
|0|1|0|5|
|0|0|1|2|

=>
$$x_1 = 2$$
$$x_2 = 5$$
$$x_3 = 2$$

## Überladen
n = 3 Variablen
m = 4 Gleichungen

=>
$$\left(\begin{array}{ccc|c} a_{11} & a_{12} & a_{13} & b_1 \\ a_{21} & a_{22} & a_{23} & b_2 \\ a_{31} & a_{32} & a_{33} & b_3 \\ a_{41} & a_{42} & a_{43} & b_4 \end{array}\right)$$

=>
$$\left(\begin{array}{ccc|c} 1 & 0 & 0 & b_1` \\ 0 & 1 & 0 & b_2` \\ 0 & 0 & 1 & b_3` \\ 0 & 0 & 0 & b_4` \end{array}\right)$$

Von $c_4$ hängt ab, ob es eine Lösung gibt:

$b_4` \neq 0$: Es gibt keine Lösung
$b_4` = 0$: 4rte Zeile ist unnötig, es gibt also eine Lösung

## Unterladen
n = 3 Variablen
m = 2 Gleichungen

=>
$$\left(\begin{array}{ccc|c} a_{11} & a_{12} & a_{13} & b_1 \\ a_{21} & a_{22} & a_{23} & b_2 \end{array}\right)$$

=>
$$\left(\begin{array}{ccc|c} 1 & 0 & a_{13}` & b_1` \\ 0 & 1 & a_{23}` & b_2` \end{array}\right)$$

Da $m < n$, gibt es mehr Variablen als Gleichungen. Nach dem Pivot Verfahren bleibt mindestens eine Variable frei wählbar (freie Variable).

$x_3 = t \in \mathbb{R}$ (freie Variable)

$$x_1 = b_1` - a_{13}` \cdot t$$
$$x_2 = b_2` - a_{23}` \cdot t$$

=> Es gibt **unendlich viele Lösungen**

Vektordarstellung: 

$$\begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} = \begin{pmatrix} b_1` \\ b_2` \\ 0 \end{pmatrix} + t \cdot \begin{pmatrix} -a_{13}` \\ -a_{23}` \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}$$
