---
Dozent: Holey
tags:
- übung
---
# Lineare Gleichungssysteme
Ein Gleichungssystem ist ein LGS, sofern keine Potenzen der Variablen enthalten sind
**Eigenschaften**:
- Immer entweder eine, keine oder unendlich Lösung/en
- nur lineare Funktionen

# Gauß Verfahren
Zur Lösung eines LGS:
- Zeilen dürfen multipliziert werden (ausgenommen 0)
- Zeilen dürfen addiert werden

Man eleminiert eine Variable durch ein Pivot element, indem man eine Zeile von der Anderen Subtrahiert. 
Bsp:
$$\begin{array}{rcrcrcrl} (1) & 1x & + & 2y & + & 1z & = & 8 \\ (2) & 2x & + & 1y & - & 1z & = & 1 \\ (3) & 1x & - & 1y & + & 2z & = & 7 \end{array}$$

Eleminierung von X:
- $(2) - 2 \times (1)$
    
    $$\begin{array}{rcrcrcrl} & (2x + 1y - 1z) & - & 2(1x + 2y + 1z) & = & 1 - 2(8) \\ \implies & 0x & - & 3y & - & 3z & = & -15 \end{array}$$
    
- $(3) - (1)$
    
    $$\begin{array}{rcrcrcrl} & (1x - 1y + 2z) & - & (1x + 2y + 1z) & = & 7 - 8 \\ \implies & 0x & - & 3y & + & 1z & = & -1 \end{array}$$

$$\begin{array}{rcrcrcrl} (1) & 1x & + & 2y & + & 1z & = & 8 \\ (2') & & - & 3y & - & 3z & = & -15 \\ (3') & & - & 3y & + & 1z & = & -1 \end{array}$$

Eleminierung von Y:
- $(3') - (2')$

	$$\begin{array}{rcrcrcrl} & (-3y + 1z) & - & (-3y - 3z) & = & -1 - (-15) \\ \implies & 0y & + & 4z & = & 14 \quad \implies \mathbf{4z = 14} \end{array}$$

$$\begin{array}{rcrcrcrl} (1) & 1x & + & 2y & + & 1z & = & 8 \\ (2') & & - & 3y & - & 3z & = & -15 \\ (3'') & & & & & 4z & = & 14 \end{array}$$

Auflösen nach Z in (3''), danach Y in (2'), danach X in (1):

**Lösung:** $(x, y, z) = (1{,}5 \;;\; 1{,}5 \;;\; 3{,}5)$
