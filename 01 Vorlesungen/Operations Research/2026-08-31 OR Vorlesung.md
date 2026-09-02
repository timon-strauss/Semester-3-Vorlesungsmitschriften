---
Dozent: Holey
tags:
- Vorlesung
---
# LGS
$A · x = b$: Lineares Gleichungssystem => WDH-LGS.pdf

LGS Lösen mit **Pivot** Verfahren: [[Übung Or Pivot Verfahren]]
- Variablenanzahl => n
- Gleichungsanzahl => m

$I: n = m$: i.d.R eine Lösung
$I: n < m$: i.d.R keine Lösung
$I: n > m$: i.d.R unendlich Lösungen

# Optimierungen

Aus Ungleichungen mach Gleichungen durch zusätzliche Variablen => Schlupfvariable
=> Bsp. $x \geq y <=> x + s_1 = y,\ s_1 \geq 0$

## Grafische Darstellung
$I$: Variablen als x,y-Achse in einem Koordinatensystem aufstellen
$II$: Nebenbedingungen als Geraden aufstellen => Halbebenen
$III$: Eingegrenzter Bereich: Lösungsgebiet: Alle möglichen Lösungen sind dort, optimalstes finden!

Nun kann die Zielfunktion $z(x,y) = z_k = ax + by$ umgestellt werden zu der Geraden:
$$y = -\frac{ax}{b} + \frac{z_k}{b}$$

$z_k$ wird hierfür zunächst beliebig gewählt => Alle Geraden nach $z_k$ sind parallell, da die Steigung gleich ist!
Nun kann die optimalste Gerade über Bestimmung von $z_k$ bestimmt werden, indem diejenige Gerade bestimmt wird, die einen Eckpunkt tangiert.
- Für Maximum: Ecke auf der rechten Seite
- Für Minimum: Ecke auf der linken Seite

Das $z_k$, für welches die Gerade den Eckpunkt tangiert, wird $z_max$, bzw $z_min$ betitelt!

## Übertragung auf n > 2
**Lineares Optimierungsproblem in Standardform**:
- Nur positive Variablen
- nur Gleichungen

**Eigenschaften Linearer Optimierungsprobleme in Standardform**:
- Konvexe Lösungsmenge => zwischen 2 Punkten in der Lösungsmenge existiert **immer** eine Linie, welche innerhalb der Lösungsmenge liegt. Es gibt keine Lücken!
- Optimum ist immer ein Eckpunkt
- Eckpunkte sind Punkte, in denen $n-m$ Variablen (incl. Schlupfvariablen) 0 sind
=> Eckpunkte sind, wenn min. $n-m$ Bedingungen zum Maximum ausgereizt sind, also sich die Geraden von $n-m$ Nebenbedingungen schneiden

## Simplex-Verfahren
**Annahme**: Sobald man einen Eckpunkt gefunden hat, dessen benachbarte Eckpunkte von einem kleineren $z_k$-Gerade durchdrungen werden, gefunden hat, hat man das Optimum gefunden.

**Vorraussetzung**: Lineareres Optimierungsproblem in Standardform
- => Konvexe Lösungsmenge
- => Lineare Funktionen

**Grund**:  Konvex garantiert immer, dass es keine lokalen Maxima und Minima gibt
=> Hat man ein lokales Maxima gefunden, muss es global sein: Annahme bestätigt
 
# Todo
- [x] #task OR: Pivot Verfahren anschauen
- [x] #task OR: 2.2 & 2.3 Wiederholen