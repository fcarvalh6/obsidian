#HS2025 #LA 

## Matrix-Formen

**Def 3.1:** Ein lineares Gleichungssystem mit $m$ Gleichungen und $n$ Variablen $x_{1},x_{2},\dots,x_{n}$ ist von der Form

$$
\begin{align}
a_{11}x_{1} + a_{12}x_{2}+\dots+a_{1n}x_{n}&=b_{1} \\
a_{21}x_{1} + a_{22}x_{2}+\dots+a_{2n}x_{n}&=b_{1} \\ \\
& \vdots \\
a_{m 1}x_{1} + a_{m 2}x_{2}+\dots+a_{mn}x_{n} &= b_{m}
\end{align}
$$

Die $a_{ij}, b_{i}$: bekannte reelle Zahlen. Die $x_{j}$: unbekannte reelle Zahlen (zu bestimmen).

**Matrix-Vektor-Form**

$$
A\mathbf{x=\mathbf{b}}:\begin{bmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n}  \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1}  & a_{m 2} & \dots & a_{m n}
\end{bmatrix}\begin{pmatrix}
x_{1} \\
x_{2} \\
\vdots \\
x_{n}
\end{pmatrix}=\begin{pmatrix}
b_{1} \\
b_{1} \\
\vdots \\
b_{m}
\end{pmatrix}
$$

$A:$ Koeffizientenmatrix, $\mathbf{x}$: Variablenvektor, $\mathbf{b}$: rechte Seite

Lösen des Systems: finde $x\in \mathbb{R}^{n}$ mit $A\mathbf{x}=\mathbf{b}$ oder berichte, dass es keinen solchen Vektor gibt. 

$A$ in Zeilennotation

$$
A=\begin{bmatrix}
- & u_{1}^T & - \\
- & u_{2}^T & - \\
 & \vdots &  \\
- & u_{m}^T & -
\end{bmatrix}:
$$

Erfülle alle $m$ Gleichungen $u_{i}^T\mathbf{x}=b_{i}, i= 1,2,\dots,m$.

A in Spaltennotation

$$
A=\begin{bmatrix}
\mid & \mid &  & \mid \\
\mathbf{v}_{1} & \mathbf{v}_{2} & \dots & \mathbf{v}_{n} \\
\mid & \mid &  & \mid
\end{bmatrix}
$$

Schreibe $\mathbf{b}$ als Linearkombination von $\mathbf{v_{1}},\mathbf{v_{2}},\dots,\mathbf{v}_{n}$

$$
\mathbf{b}=\sum_{j=1}^nx_{j}v_{j}
$$

## Invertieren einer Matrix

$m\times m$ Matrix $A$ invertierbar $\iff$ es gibt $m\times m$ Matrix B mit $AB=I$

$$
B=\begin{bmatrix}
\mid & \mid &  & \mid \\
\mathbf{x_{1}} & \mathbf{x}_{2} & \dots & \mathbf{x}_{m} \\
\mid & \mid &  & \mid
\end{bmatrix}:
$$

$$
AB=\begin{bmatrix}
\mid & \mid &  & \mid \\
A\mathbf{x_{1}} & A\mathbf{x}_{2} & \dots & A\mathbf{x}_{m} \\
\mid & \mid &  & \mid
\end{bmatrix} = \begin{bmatrix}
\mid & \mid &  & \mid \\
\mathbf{e}_{1} & \mathbf{e}_{2} & \dots & \mathbf{e}_{m} \\
\mid & \mid &  & \mid
\end{bmatrix}=I
$$

Um $x_{j}$ (Spalte $j$ von $B$), löse $A\mathbf{x}=\mathbf{e}_{j}$. Um $B$ zu finden, löse $m$ lineare Gleichungssysteme.

## Gauss-Elimination

Algorithmus zum Lösen von $A\mathbf{x}=\mathbf{b}$ mit quadratische $A$:

1. Transformiere $A\mathbf{x}=\mathbf{b}$ in ein System $U\mathbf{x}=\mathbf{c}$ mit den gleichen Lösungen, aber "hübschem" $U$ (obere Dreiecksmatrix).
2. $U\mathbf{x}=\mathbf{c}$ kann leicht gelöst werden.

**Rückwärts...**

Fall $m\times m:$ Gleichung $i=m,m-1,\dots,1:$

$$
\sum_{j=i}^m u_{ij}x_{j}=c_{i}
$$

oder

$$
x_{i}=\frac{c_{i}-\sum_{j=i+1}^m u_{ij}x_{j}}{u_{ii}}
$$

Braucht $u_{ii}\not=0$ für alle $i$

Wir kennen $x_{m},x_{m-1},\dots,x_{i+1}$ schon. Nun kennen wir auch $x_{i}$. 

**Elimination:** wenn $A$ keine obere Dreiecksmatrix ist. $A\mathbf{x}=\mathbf{c}\to U\mathbf{x}=\mathbf{c}$

% - complete w/ script

