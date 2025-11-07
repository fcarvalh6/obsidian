#HS2025 #AD 

## Teilsumme (subset sum)

**Gegeben:** $A[1\dots n]$ und $b$, alles in $\mathbb{N}$ 

**Gesucht:** $I=\{ 1\dots n \}$ sodass $\sum_{i\in I}A[i]=b$

**Beispiel:** $A=[5,3,10,3,1]$ $b=9$ möglich, $b=12$ möglich, $b=2$ nicht möglich, $b=23$ n.m.

### Teilproblem

$T(i,s)=$ "Ist $s$ eine Teilsumme von $A[1\dots i]$" $\in \{ 0,1 \}$

**Rekursion: **$T(i,s)=T(i-1,s)\lor T(i-1,s-A[i])$ (benutze/benutze nicht $A[i]$, $0,$ falls $s<A[i]$)

$T(i,0)=1$ und $T(0,s)=0$ für $s\ge 1$ 

Laufzeit $O(b\cdot n)$
- $n:$ Anzahl der Zahlen im Input
- $b:$ einzelne Zahl im Input
- Referenzgrösse: Länge des Inputs.
- Inputlänge: $O(n+1)$, wobei $1$ ist $O(\log b)$ Bits
- Beispiel: $b=2^{n}:$ Inputlänge $O(n)$, Laufzeit $O(n 2^{n})$ 

## Rucksackproblem (knapsack)

**Gegeben:** Rucksack mit Gewichtslimit $W$, $n$ Gegenstände mit Gewicht $w\in \mathbb{N}$ und profit $p\in \mathbb{N}$ 

**Gesucht:** Teilmenge $I\subseteq \{ 1,\dots,n \}$ mit $\sum_{i\in I}w_{i}\le W$ und $\sum_{i\in I}p_{i}$ maximal

### Teilproblem

$P(i,w)=$ maximaler Profit, den wir von $A[1\dots i]$ mit Gewichtslimit $w$ erreichen können

**Rekursion:** $P(i,w)=\text{max}\{ P(i-1,w),p_{i}+P(i-1,w-w_{i}) \}$, 2. nur wenn $w\le w_{i}$

**Laufzeit:** $O(W\cdot n)$ (nicht pseudo-polynomiell) 

### Alternatives Teilproblem

$G(i,p)=$ minimale Gewicht, mit dem man Profit $\ge p$ aus $A[1\dots i]$ erzeugen kann.

**Rekursion:** $G(i,p)=\text{min}\{ G(i-1,p),w_{i}+G(i-1,p-p_{i}) \}$ 

**Laufzeit:** $O(P\cdot n)$ 

Geht es besser (polynomiell)? Vermutung: nein.

## P vs NP

$P:=$ Menge aller Probleme, die in polynomieller Zeit lösbar sind.

$NP:=$ Menge aller Probleme, bei denen wir eine Lösung in polynomieller Zeit prüfen können. 

Vermutung: $P\not= NP$ 

Tiefer mathematischer Satz: 
- polynomieller Algorithmus für *subset sum*/*knapsack*/*etc.* $\implies P=NP$ 

## Approximationsalgorithmus

**Input:** $w_{i},p_{i}, W\in \mathbb{N}$

**Ziel:** Lösung die fast optimal ist

**Idee:** Runden. 
- Wähle $k\in \mathbb{N}$
- ersetze $p_{i}$ durch $\tilde{p_{i}}:= k\left\lfloor  \frac{p_{i}}{k}  \right\rfloor$
- $w$ und $W$ bleiben unverändert $\to$ dieselben Teilmengen wie vorher passen in dem Rucksack. 

$p_{i}\stackrel{\text{DP}}\to\text{OPT}\subseteq \{ 1,\dots,n \}$, Profit $P_{opt}$, Laufzeit $O(nP)$, zu langsam

$\tilde{p_{i}}\stackrel{\text{DP}}\to\tilde{\text{OPT}}\subseteq \{ 1,\dots,n \}$, Profit ??, Laufzeit $O(n\tilde{P} / k)$ 

Beobachtung: $p_{i}-k < \tilde{p_{i}} \le p_{i}\le p_{\text{max}}\le P_{opt}$

Wie gut ist $\tilde{\text{OPT}}$ für das Ursprungsproblem? $\sum_{i\in \text{OPT}}p_{i}$ untersuchen.

Wissen: $\tilde{\text{OPT}}$ optimal für $p_{i}\implies$ Für jede Teilmenge $I$ die in den Rucksack passt, gilt 

$$
\sum_{i\in\text{OPT}}\tilde{p_{i}}\ge \sum_{i\in I}\tilde{p_{i}}
$$

$I=\text{OPT}\implies$

$$
\sum_{i\in \tilde{\text{OPT}}} \tilde{p_{i}} \ge \sum_{i\in \text{OPT}}\tilde{p_{i}} \quad (*)
$$

$$
\sum
$$
%

## Längste Aufsteigende Teilfolge

**Gegeben:** Array $A[1\dots n]$ von Integers

**Gesucht:** Länge der/einer längsten aufsteigenden Teilfolge.

$[2,13,17,9,11,4,78,28,15,25,99]$

### Teilproblem (Versuch 1,2)

$\text{LAT}(i):=$ eine/alle LAT in $A[1\dots i]$ 

### Teilproblem (Versuch 3)

$E(i,l):=$ "Es gibt AT der Länge $l$, die in $i$ endet" $\in \{ 0,1 \}$

**Rekursion ($l\ge 2)$** 

$$
E(i,l)=\begin{cases}
1,\text{ falls es }j<i \text{ gibt mit } E(j,l-1)\text{ und }A[j]<A[i] \\
0,\text{ sonst} 
\end{cases}
$$

$E(i,1)=1$

**Laufzeit:** $O(n^{3})$ 

### Teilproblem (Versuch 4):

$M(i,l):=$ kleinstmögliche Endung einer AT in $A[1\dots i]$ 

**Rekursion $(i\ge 2):$** 

$$
M(i,l)=\begin{cases}
A[i], \text{falls }M(i-1,l-1)<A[i]<M(i-1,l) \\
M(i-1,l)
\end{cases}
$$

$$
M(1,l)=\begin{cases}
A[1] & \text{ falls } l=1 \\
\infty & \text{ falls } l > 1
\end{cases}
$$

**Laufzeit:** $O(n^{2})$ 

**Beobachtung:**
- Die Zeilen sind sortiert
- Wir ändern nur einen Wert pro Zeile
	- können wir in Zeit $O(\log n)$ finden
- Wenn wir die Zeile nicht kopieren, sondern nur den einen Wert überschreiben, benötigt wir Zeit $O(n\log n)$ 

