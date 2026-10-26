---
tags:
  - investition
  - finanzierung
  - klausur
  - formelsammlung
cssclasses:
  - wide-page
---

# 📐 Formelblatt — Investition & Finanzierung

> [!abstract] Nur Rechenformeln
> Keine Theorie, keine Beispiele. Durchgerechnete Musterlösungen → [[Formelsammlung]] · Lernreihenfolge → [[Lernplan]]

### Symbole

| Symbol | Bedeutung | Symbol | Bedeutung |
|:--|:--|:--|:--|
| $AK$ | Anschaffungskosten | $x$ | Ausbringungsmenge |
| $RW$ | Restwert / Liquidationserlös | $p$ | Preis pro Stück |
| $n$ | Nutzungsdauer bzw. Laufzeit in Jahren | $K_f$ | Fixkosten gesamt |
| $i$ | Zinssatz als Dezimalzahl | $k_v$ | variable Kosten pro Stück |
| $q$ | $1 + i$ | $Z_t$ | Einzahlungsüberschuss in Jahr $t$ |

---

## 1 · Kapitalerhöhung / Aktien

### Bezugsverhältnis

$$
\text{Kapitalerhöhung} = GK_{neu} - GK_{alt}
$$

$$
BV = \frac{GK_{alt}}{\text{Erhöhungskapital}}
$$

### Bezugsrecht und Mischkurs

$$
BR = \frac{K_{alt} - K_{neu}}{BV + 1}
\qquad\qquad
M = \frac{BV \cdot K_{alt} + K_{neu}}{BV + 1}
$$

$$
BR = K_{alt} - M \qquad \text{(Probe bzw. „ohne Formel")}
$$

### Stückzahlen

$$
\text{Nennwert} = \frac{\text{Grundkapital}}{\text{Anzahl aller Aktien}}
\qquad\qquad
A_{jung} = \frac{\text{Erhöhungskapital}}{\text{Nennwert}}
$$

### Investitionskosten eines Aktionärs

$$
BR_{\text{benötigt}} = N_{jung} \cdot BV
$$

$$
\text{Aufwand} = \bigl(BR_{\text{benötigt}} - BR_{\text{vorhanden}}\bigr) \cdot BR \;+\; N_{jung} \cdot K_{neu}
$$

### Bilanzwirkung

$$
\begin{aligned}
\text{Bank} \;&=\; A_{jung} \cdot K_{neu} \\[4pt]
\text{Gez. Kapital} \;&=\; A_{jung} \cdot \text{Nennwert} \\[4pt]
\text{Kapitalrücklage} \;&=\; A_{jung} \cdot \bigl(K_{neu} - \text{Nennwert}\bigr)
\end{aligned}
$$

$$
\text{Probe:}\quad \text{Bank} = \text{Gez. Kapital} + \text{Kapitalrücklage}
$$

> [!warning] Lesart des Bezugsverhältnisses
> $BV = 7{:}2$ → in jede Formel **$BV = 3{,}5$** einsetzen.
> $BR_{\text{vorhanden}}$ = Anzahl der Altaktien · $K_{alt}$ = Börsenkurs alte Aktie · $K_{neu}$ = Ausgabe-/Bezugskurs junge Aktie

---

## 2 · Darlehen

### Für jede Zeile jedes Tilgungsplans

$$
\begin{aligned}
\text{Zinsen}_t \;&=\; \text{Restschuld}_{t,\,\text{Anfang}} \cdot i \\[4pt]
\text{Zahlbetrag}_t \;&=\; \text{Zinsen}_t + \text{Tilgung}_t \\[4pt]
\text{Restschuld}_{t,\,\text{Ende}} \;&=\; \text{Restschuld}_{t,\,\text{Anfang}} - \text{Tilgung}_t
\end{aligned}
$$

### Annuitätendarlehen

$$
e = K_0 \cdot \underbrace{\frac{q^n \cdot (q-1)}{q^n - 1}}_{KWF} = K_0 \cdot KWF
$$

$$
\text{Tilgung}_t = e - \text{Zinsen}_t
\qquad\qquad
\text{Zahlbetrag}_t = e \;\; \text{(konstant)}
$$

### Festdarlehen (Fälligkeitsdarlehen)

$$
\text{Zinsen} = K_0 \cdot i \;\;\text{(konstant)}
\qquad\qquad
\text{Tilgung}_t =
\begin{cases}
0 & t = 1, \dots, n-1 \\
K_0 & t = n
\end{cases}
$$

### Abzahlungsdarlehen (Ratentilgung)

$$
\text{Tilgung} = \frac{K_0}{n} \;\;\text{(konstant)}
$$

---

## 3 · Kalkulatorische Kosten

### Kalkulatorische Abschreibung

$$
\text{kalk. AfA} = \frac{AK}{n}
\qquad\qquad
\text{kalk. AfA} = \frac{AK - RW}{n}
$$

$$
\small \text{ohne Restwert} \qquad\qquad\qquad\qquad\quad \text{mit Restwert}
$$

### Kalkulatorische Zinsen

$$
\overline{K} = \frac{AK}{2}
\qquad\qquad
\overline{K} = \frac{AK + RW}{2}
$$

$$
\small \text{ohne Restwert} \qquad\qquad\qquad\qquad\quad \text{mit Restwert}
$$

$$
Z = \overline{K} \cdot i
$$

> [!danger] Die häufigste Falle der Klausur
> $$\text{AfA}: \; AK \;\boldsymbol{-}\; RW \qquad\qquad \text{Zinsen}: \; AK \;\boldsymbol{+}\; RW$$
> Bei der AfA wird nur der *verbrauchte* Teil abgeschrieben → **minus**.
> Bei den Zinsen ist der Restwert über die ganze Laufzeit *mitgebunden* → **plus**.

---

## 4 · Kostenvergleichsrechnung

$$
K(x) = K_f + k_v \cdot x
\qquad\qquad
k(x) = \frac{K(x)}{x}
$$

### Zusammensetzung

$$
\begin{aligned}
K_f \;&=\; \text{kalk. AfA} + \text{kalk. Zinsen} + \text{Gehälter} + \text{sonst. fixe Kosten} \\[4pt]
k_v \;&=\; \text{Löhne/St.} + \text{Material/St.} + \text{sonst. variable Kosten/St.}
\end{aligned}
$$

### Kritische Ausbringungsmenge

$$
K_{f_1} + k_{v_1} \cdot x \;=\; K_{f_2} + k_{v_2} \cdot x
$$

$$
\boxed{\; x_{krit} = \frac{K_{f_1} - K_{f_2}}{k_{v_2} - k_{v_1}} \;}
$$

> [!tip] Interpretation
> Unterhalb $x_{krit}$ ist die Alternative mit den **niedrigeren Fixkosten** günstiger, oberhalb die mit den **niedrigeren variablen Kosten**.

---

## 5 · Gewinnvergleichsrechnung

$$
G = U - K = p \cdot x - \bigl(K_f + k_v \cdot x\bigr)
$$

$$
G = \underbrace{(p - k_v)}_{\text{Stückmarge}} \cdot x \; - \; K_f
$$

### Kritische Menge

$$
p_1 x - k_{v_1} x - K_{f_1} \;=\; p_2 x - k_{v_2} x - K_{f_2}
$$

$$
x_{krit} = \frac{K_{f_1} - K_{f_2}}{(p_1 - k_{v_1}) - (p_2 - k_{v_2})}
$$

---

## 6 · Rentabilitätsvergleichsrechnung

$$
\boxed{\;
R = \frac{GvZ}{\dfrac{AK + RW}{2}} \cdot 100 \quad [\%]
\;}
$$

$$
GvZ = \text{Erlöse} - \text{Kosten}_{\text{ohne kalk. Zinsen}}
$$

> [!warning] Zentrale Abweichung
> Die **kalkulatorischen Zinsen** werden hier **nicht** als Kosten abgezogen — die kalkulatorische **AfA bleibt** enthalten.
> In der Kostentabelle also die Zeile „Kalk. Zinsen" **streichen**, „Kalk. AfA" **behalten**.

---

## 7 · Statische Amortisationsrechnung

### Durchschnittsrechnung

$$
AZ = \frac{AK - RW}{\text{Gewinn} + \text{AfA}} = \frac{AK - RW}{\varnothing \text{ jährliche Rückflüsse}}
$$

### Kumulationsrechnung

Zahlungsflüsse kumulieren → amortisiert im **ersten Jahr mit kumulierter Summe $\geq 0$**.

$$
AZ = t^{-} + \frac{\bigl|\text{Kumulierter Rest in } t^{-}\bigr|}{\text{Zahlungsfluss in } t^{-}+1}
$$

mit $t^{-}$ = letztes Jahr mit negativer kumulierter Summe.

---

## 8 · Kapitalwertmethode

### Abzinsung einer einzelnen Zahlung

$$
BW = K_n \cdot \frac{1}{q^{\,n}} = \frac{K_n}{(1+i)^n}
$$

### Kapitalwert

$$
\boxed{\;
K_0 = -AK + \sum_{t=1}^{n} \frac{Z_t}{(1+i)^t} + \frac{RW}{(1+i)^n}
\;}
$$

### Entscheidungsregel

| Fall | Aussage | Entscheidung |
|:--|:--|:--|
| $K_0 > 0$ | erwirtschaftet **mehr** als die Mindestverzinsung | durchführen |
| $K_0 = 0$ | deckt genau Zinsen und Kapital | indifferent |
| $K_0 < 0$ | unterschreitet die Mindestverzinsung | ablehnen |

> [!tip] Jahr 0 und Restwert
> $AK$ steht in Jahr $0$ mit **negativem** Vorzeichen und wird **nicht** abgezinst $\bigl(q^0 = 1\bigr)$.
> Der Restwert wird mit dem Faktor des **letzten** Jahres abgezinst, also $1/q^{\,n}$.

---

## 9 · Dynamische Amortisationsrechnung

Tabellenaufbau:

| Jahr $t$ | Rückfluss $Z_t$ | Barwert $\dfrac{Z_t}{q^{\,t}}$ | Barwerte kumuliert |
|:--:|--:|--:|--:|

Amortisation im **ersten Jahr mit kumuliertem Barwert $\geq 0$**.

$$
AZ = t^{-} + \frac{\bigl|\text{Kumulierter Barwert in } t^{-}\bigr|}{\text{Barwert in } t^{-}+1}
$$

---

## 10 · Zins-Faktoren

### Abzinsungsfaktoren $\dfrac{1}{q^{\,n}}$

| $n$ | $i = 8\%$ | $i = 10\%$ | $i = 12\%$ |
|:--:|--:|--:|--:|
| 1 | 0,9259 | 0,9091 | 0,8929 |
| 2 | 0,8573 | 0,8264 | 0,7972 |
| 3 | 0,7938 | 0,7513 | 0,7118 |
| 4 | 0,7350 | 0,6830 | 0,6355 |
| 5 | 0,6806 | 0,6209 | 0,5674 |
| 6 | 0,6302 | 0,5645 | 0,5066 |
| 7 | 0,5835 | 0,5132 | 0,4523 |
| 8 | 0,5403 | 0,4665 | 0,4039 |
| 9 | 0,5002 | 0,4241 | 0,3606 |
| 10 | 0,4632 | 0,3855 | 0,3220 |

### Aufzinsungsfaktoren $q^{\,n}$

| $n$ | $1{,}08^n$ | $1{,}10^n$ | $1{,}12^n$ |
|:--:|--:|--:|--:|
| 1 | 1,08000 | 1,10000 | 1,12000 |
| 2 | 1,16640 | 1,21000 | 1,25440 |
| 3 | 1,25971 | 1,33100 | 1,40493 |
| 4 | 1,36049 | 1,46410 | 1,57352 |
| 5 | 1,46933 | 1,61051 | 1,76234 |
| 6 | 1,58687 | 1,77156 | 1,97382 |
| 7 | 1,71382 | 1,94872 | 2,21068 |
| 8 | 1,85093 | 2,14359 | 2,47596 |

---

## 🧾 Schmierblatt — in den ersten 60 Sekunden hinschreiben

$$
\begin{aligned}
\text{AfA} &= \frac{AK - RW}{n} &&\text{← MINUS} \\[8pt]
Z &= \frac{AK + RW}{2} \cdot i &&\text{← PLUS} \\[8pt]
BV &= \frac{GK_{alt}}{KE} \quad BR = \frac{K_{alt} - K_{neu}}{BV+1} \quad M = \frac{BV \cdot K_{alt} + K_{neu}}{BV+1} \\[8pt]
e &= K_0 \cdot \frac{q^n (q-1)}{q^n - 1} &&\text{Zinsen auf Restschuld ANFANG} \\[8pt]
R &= \frac{GvZ}{(AK+RW)/2} \cdot 100 &&\text{← GvZ ohne kalk. Zinsen} \\[8pt]
K_0 &= -AK + \sum_{t=1}^{n} \frac{Z_t}{q^{\,t}} + \frac{RW}{q^{\,n}} &&K_0 > 0 \Rightarrow \text{durchführen}
\end{aligned}
$$
