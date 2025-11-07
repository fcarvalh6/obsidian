#HS2025 #LA 

## Lineare Transformationen zwischen Vektorräumen

**Def. 4.26:** Seien $V,W$ zwei Vektorräume. Eine Funktion $T:V\to W$ heisst lineare Transformation (zwischen Vektorräumen), wenn Linearität für alle $x_{1},x_{2}\in V$ und $\lambda_{1},\lambda_{2}\in \mathbb{R}$ gilt: 

$$
T(\underbrace{\lambda_{1}x_{1}+\lambda_{2}x_{2}}_{\in V})=\lambda_{1}\underbrace{T(x_{1})}_{\in W}+\underbrace{\lambda_{2}T(x_{2})}_{\in W}
$$

Bisher: $V\text=\mathbb{R}^{n},W=\mathbb{R}^{m}$

Anderes Beispiel: Matrix "Flachdrücken" 

$$
V=\mathbb{R}^{2\times2},W=\mathbb{R}^{4},T:\begin{bmatrix}
a & b \\
c & d
\end{bmatrix} \mapsto \begin{pmatrix}
a \\
b \\
c \\
d
\end{pmatrix}
$$

Das ist bijektiv (umkehrbar).

**Def. 4.28:** Sei $T:V\to W$ lineare Transformation, bijektiv. Dann heissen $V$ und $W$ isomorph, und $T$ ist Isomorphismus zwischen $V$ und $W$.

Beispiele:
- $V=\mathbb{R}^{m\times n},W=\mathbb{R}^{m\cdot n},T$ die Flachdrücktransformation
- $V=$ Polynome von Grad $\le 2$, $W=\mathbb{R}^{3},T:p_{0}+p_{1}x+p_{2}x^{2}\to\begin{pmatrix}p_{0} \\ p_{1} \\ p_{2}\end{pmatrix}$
## Berechnung (von Basen) der Fundamentalen Unterräume

Spaltenraum $C(A)$, Zeilenraum $R(A)$, Nullraum $N(A)$.

Basiert auf $A\to R$ (Gauss-Jordan)

### Spaltenraum

**Theorem 4.31:** wenn $R$ in $\text{RREF}(j_{1},j_{2},\dots,j_{r})$, dann hat $A$ die unabhängigen Spalten an Positionen $j_{1},j_{2},\dots,j_{r}$, und diese Spalten bilden eine Basis von $C(A)$. Insbesondere gilt $\text{dim}(C(A))=\text{rang}(R)=r$ 

Beweis: Unabhängige Spalten = Basis von $C(A)$
- (Lemma 4.19) und $R$ gibt uns ihre Positionen in $A$ (Theorem 3.18). Also $\text{dim}(C(A))=r$ (Def. 4.25) und $\text{rang}(A)=r$ (Def. 2.10)

### Zeilenraum

**Theorem 4.32:** wenn $R$ in $\text{RREF}(j_{1},j_{2},\dots,j_{r})$, dann bilden die ersten $r$ Zeilen von $R$ eine Basis von $R(A)$. Insbesondere gilt $\text{dim}(R(A))=r$. 

Beweis: $R=MA$ mit $M$ invertierbar (Theorem 3.17) $\implies R$ und $A$ haben den gleichen Zeilenraum (Lemma 3.5). Die $r$ Nichtnullzeilen von $R$ spannen den Zeilenraum von $R$ bereits auf und sind linear unabhängig (private Nichtnullen bei den Stufen). Also sind die ersten $r$ Zeilen nach Definition eine Basis von $R(A)$ und $\text{dim}(R(A))=r$.

**Theorem 4.33:** Sei $A$ eine $m\times n$ Matrix. Dann gilt $\text{rang}(A)=\text{rang}(A^{T})$.

Beweis:
- $\text{rang}(A)=\text{dim}(C(A))=r$ (Theorem 4.31)
- $\text{rang}(A^{T})=\text{dim}(C(A^{T}))=\text{dim}(R(A))=r$ (Theorem 4.32)

**Korollar 4.34:** Sei $A$ eine $m\times n$ Matrix mit Rang $r$. Dann gilt $r\le\text{min}(m,n)$. 

Beweis: $r =\text{rang}(A)\le n, r=\text{rang}(A^{T})\le m$ 

### Nullraum

**Lemma 3.3:** $N(A)=N(R)=N(R')$

Dimension/Basis per Beispiel:

$x\in N(R')\iff R'\mathbf{x}=0$, und das kann so geschrieben werden: 

$$
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}\begin{pmatrix}
x_{1} \\
x_{2}
\end{pmatrix}+\begin{bmatrix}
2 & 3 \\
0 & -2
\end{bmatrix}\begin{pmatrix}
x_{2} \\
x_{4}
\end{pmatrix}=0
$$

oder 

$$
\begin{pmatrix}
x_{1} \\
x_{3}
\end{pmatrix}=-\begin{bmatrix}
2 & 3 \\
0 & -2
\end{bmatrix}\begin{pmatrix}
x_{2} \\
x_{4}
\end{pmatrix} \quad (*)
$$

$\implies N(R')$ ist isomorph $\mathbb{R}^{n-r}$ und hat deshalb Dimension $n-r$ (Lemma 4.27)

$$
T:\begin{pmatrix}x_{1} \\ x_{2} \\ x_{3} \\ x_{4}\end{pmatrix} \mapsto \begin{pmatrix}
x_{2} \\
x_{4}
\end{pmatrix}
$$

ist eine bijektive lineare Transformation: zu jeder möglichen Ausgabe $\begin{pmatrix}x_{2} \\ x_{4}\end{pmatrix}$ führt genau eine Eingabe $\begin{pmatrix}x_{1} \\ x_{2} \\ x_{3} \\ x_{4}\end{pmatrix}$ , die fehlenden Werte $x_{1},x_{2}$ erhalten wir aus $(*)$ 

Basis von $N(A)$ und $N(R'):$ Eingaben, die zu den Ausgaben $e_{1},e_{2},\dots,e_{n-r}$ führen (Theorem 4.36)

## Alle Lösungen von $A\mathbf{x}=\mathbf{b}$

**Def. 4.37:** Sei $A$ $m\times n$ Matrix, $\mathbf{b}\in \mathbb{R}^{m}$. Die Menge $\text{Sol}(A,\mathbf{b})=\{ x\in \mathbb{R}^{n}:A\mathbf{x}=\mathbf{b} \}\subseteq \mathbb{R}^{n}$ ist der Lösungsraum von $A\mathbf{x}=\mathbf{b}$. 
- **kein** Unterraum, wenn $\mathbf{b}\not=0$, weil dann $0\not\in\text{Sol}(A,\mathbf{b})$.

$\text{Sol}(A,0)=N(A)$

$\text{Sol}(A,\mathbf{b})=$ "verschobener Nullraum"

**Theorem 4.38:** Sei $s$ eine Lösung von $A\mathbf{x}=\mathbf{b}$. Dann gilt: $\text{Sol}(A,\mathbf{b})=\{ s+\mathbf{x}:\mathbf{x}\in N(A) \}$

Beweis: 
1. Für jedes $\mathbf{y}\in\text{Sol}(A,\mathbf{b})$ gibt es $\mathbf{x}\in N(A)$ mit $\mathbf{y}=\mathbf{s}+\mathbf{x}$. Um das zu sehen:

$$
\mathbf{y}=\mathbf{s}+(\mathbf{y-\mathbf{s}})
$$

Dann: $A\mathbf{x}=A(\mathbf{y}-\mathbf{s})=A\mathbf{y}-A\mathbf{s}=\mathbf{b}-\mathbf{b}=0$

2. Für jeden Vektor $\mathbf{y}=\mathbf{s+\mathbf{x}}$ mit $\mathbf{x}\in N(A)$ gilt $\mathbf{y}\in\text{Sol}(A,\mathbf{b})$. Um das zu sehen:

$$
A\mathbf{y}=A(\mathbf{s}+\mathbf{x})=A\mathbf{s}+A\mathbf{x}=\mathbf{b}+0=\mathbf{b}
$$

**Theorem 4.39:** Sei $A$ $m\times n$ Matrix von Rang $r$. Wenn $A\mathbf{x}=\mathbf{b}$ eine Lösung hat, dann hat $\text{Sol}(A,\mathbf{b})$ Dimension $n-r$, wobei

$$
\text{dim}(\text{Sol}(A,\mathbf{b})):=\text{dim}(N(A))
$$

### Berechnung von Sol(A, b)

Berechne irgendeine Lösung (z.B. Gauss-Jordan, Theorem 3.20) und eine Basis $B=\{ \mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{n-r} \}$ von $N(A)$ (Theorem 4.36). Dann: 

$$
\text{Sol}(A,\mathbf{b})=\left\{  \mathbf{s}+\sum_{i=1}^{n-r}\lambda_{i}v_{i}:\lambda_{i} \in \mathbb{R}\text{ für }i\in [n\dots r]  \right\}
$$

