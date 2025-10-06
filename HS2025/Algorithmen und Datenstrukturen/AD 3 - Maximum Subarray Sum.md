#HS2025 #AD 

## Kursveränderung einer Aktie

7 -11 18 10 -23 -3 -27 -1

Wann kaufen, wann verkaufen?

### Problem: Maximum Subarray Sum
- gegeben: $a_{1},\dots,a_{2}\in \mathbb{Z}$
- gesucht: Maximale Teilsumme $S_{ij}=a_{i},\dots,a_{j},i\le j\quad i,j\in \{ 1,\dots,n \}$ und $S=0$ %

**Elementare Operation:** Addition

#### Algorithmus 1 (naiv): alle $i,j$ ausprobieren
- für alle $i=1,\dots, n$ (alle Anfänge)
- für alle $j= i,\dots, n$ (alle Enden)
$$
S_{ij}=\sum_{k=i}^ja_{k}\qquad \text{merke beste S}
$$
für $i =1,\dots,n$

| Summe                  | Operationen |
| ---------------------- | ----------- |
| $S_{i,i} = a_{i}$      | 0           |
| $Si,i+1=a_{i}+a_{i+1}$ | 1           |
| $\vdots$               | $\vdots$    |
| $S_{i,n}$              | $n-i$       |
Summe der Operationen: 

$$\frac{{(n-i)(n-1+1)}}{2}$$


**Anzahl Additionen** $A(n)$

- Abschätzung nach oben: 

$$
\frac{(n-i+1)^{2}}{2}\geq\frac{{(n-i)(n-1+1)}}{2}
$$


$$
\begin{align}
A(n)\le \sum_{i=i}^n \frac{(n-i+1)^{2}}{2} & =  \frac{1}{2}(n^{2}+(n-1)^{2}+\dots+1^{2})\\ 
& = \frac{1}{2} \frac{1}{3} (n+1)\left( n+\frac{1}{2} \right)n \leq O(n^{3})
\end{align}
$$

- Abschätzung nach unten:

$$
\begin{align}
A(n)\ge \sum_{i=1}^n \frac{1}{2}(n-1)^{2} &= \frac{1}{2}\left( (n-1)^{2} + \dots + 1^{2}+0^{2}\right) \\
&=\frac{1}{2} \frac{1}{3}(n) \underbrace{ \left( n-\frac{1}{2} \right)}_{\ge \frac{n}{2}}\underbrace{(n-1)}_{\ge \frac{n}{2}}  \\
&\ge \frac{n^{3}}{24}
\end{align}
$$

$$
n^{3}\le O(A(n))
$$

Schreibweise für gleiche Ordnung: $A(n) = \Theta(n^{3})$

#### Algorithmus 2 (Berechnungen wiederverwenden)

für $i=1,\dots,n$

$S_{i,i}=a_{i}$
$S_{i,i+1}= S_{i,i} + a_{i+1}$
$\vdots$
$S_{i,n}=S_{i,n-1},a_{n}$
$(n-i)$ Operationen

$$
A(n)=\sum_{i=1}^n(n-1)=\frac{n(n-1)}{2}=\Theta(n^{2})
$$

Bemerkung:

$$
\sum_{i=0}^n i^{2}=\frac{1}{3}n\left( n+\frac{1}{2} \right)(n+1)
$$

$$
\int_{0}^x t^{2} dt = \left[ \frac{1}{3}t^{3} \right]_{0}^x = \frac{1}{3}x^{3}
$$

#### Algorithmus 3 (rekursiv)
 
 - zerlege in 2 Hälften
	 - Fall 1: Lösung ganz links
	 - Fall 2: Lösung ganz rechts
	 - Fall 3: Lösung geht über die Mitte
- für Fall 1&2: löse rekursiv das gleiche Problem für n/2
- Fall 3: Präfixsumme + Suffixsumme
	- beste Präfixsumme rechts (n/2 viele)
		- $P_{1}=a_{\frac{n}{2}+1}$
		- $P_{2}=a_{\frac{n}{2}+2}$
		- $\vdots$
		- $P_{\frac{n}{2}}=P_{\frac{n}{2}-1}+a_{n}$
		- $\frac{n}{2}-1$ Operationen

- Teile in der Mitte $\dots$ $0$
- Löse Teilproblem links $\to M_{1}$ $\dots$ $T\left( \frac{n}{2} \right)$
- Löse Teilproblem rechts $\to M_{2}$ $\dots$ $T\left( \frac{n}{2} \right)$ 
- Beste Suffixsumme links $\dots$ $\downarrow$
- Beste Präfixsumme rechts $\dots$ $\downarrow$
- Addiere Suffix- und Präfixsummen $\to M_{3}$ $\dots$  $a\cdot n$
- $S=\text{max}(M_{1},M_{2},M_{3})$ $\dots$ $O(1)$
- return $S$
- $T(1)=C\qquad n=2^{k}$
- $T(n)=2\cdot T\left( \frac{n}{2} \right)+an, a\text{ konstant}$
- $= 2\left( 2T\left( \frac{n}{4} \right)+a \frac{n}{2} \right)+an$
- $=2^{2}T\left( \frac{n}{4} \right)+an+an$
- $\vdots$
- $= 2^{\log_{2}n}\cdot T\left( \frac{n}{n} \right)+\log_{2}n\cdot an$
- $= n \cdot C +\log_{2}n\cdot n$
- $\leq O(n\log n)$

#### Algorithmus 4 (induktiv von links nach rechts)

- Beobachtung: neues max kann nur durch $\text{randmax}+a_{i}$ entstehen

$$
\text{randmax}=0\qquad \text{max}=0
$$

für $i=1,\dots, n$ 
- $\text{randmax}= \text{randmax}+a_{i}$
- if $\text{randmax}<0 : \text{randmax}=0$
- if $\text{randmax}> \text{max}: \text{max}=\text{randmax}$
- $\leq O(n)$

