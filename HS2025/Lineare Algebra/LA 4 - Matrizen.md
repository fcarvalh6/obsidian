#HS2025 #LA 

**Korollar 1.27**: Seien $\mathbf{v_{1}},\mathbf{v_{2}},\dots,\mathbf{v_{n}} \in \mathbb{R}^{m}$ und $\mathbf{v_{k}}$ eine Linearkombination der anderen Vektoren. Dann gilt: 
$$
\text{Span}(\mathbf{v_{1}},\mathbf{v_{2}},\dots,\mathbf{v_{n}}) = \text{Span}(\mathbf{v_{1}},\mathbf{v_{2}},\dots \mathbf{v}_{k-1},\mathbf{v}_{k+1},\mathbf{v}_{k+2},\dots,\mathbf{v}_{n},\mathbf{v}_{k})
$$
**Lemma 1.28**: Seien $\mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{m} \in \mathbb{R}^{m}$ linear unabhängig. Dann gilt: $\text{Span}(\mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{m}) = \mathbb{R}^{m}$

## Matrizen und Linearkombinationen

**Matrix:** Notation für eine Folge von Vektoren:
$$
\begin{pmatrix}
1 \\
3 \\
5 \\ 
\end{pmatrix},\begin{pmatrix}
2 \\
4 \\
6
\end{pmatrix}\to\begin{bmatrix}
1 & 2 \\
3 & 4 \\
5 & 6
\end{bmatrix}
$$
**Def 2.1:** Eine $m\times n$ Matrix ist eine Tabelle reeller Zahlen mit $m$ Zeilen und $n$ Spalten.
$$
A = \begin{bmatrix}
a_{11} & a_{22} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots  & \vdots  & \ddots & \vdots\\
a_{m1} & a_{m2} & \dots &  a_{mn}
\end{bmatrix}
$$


- Punktlose Notation: $A = [a_{i j}]_{i=1,j=1}^{m\;n}$
- Spaltennotation (interpretiert die Spalten als Vektoren).
- Zeilennotation (interpretiert die Zeilen als Kovektoren)

### Matrixaddition und Skalarmultiplikation

$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}+\begin{bmatrix}
5 & 6 \\
7 & 8
\end{bmatrix}=\begin{bmatrix}
6 & 8 \\
10 & 12
\end{bmatrix}
$$

$$
2\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix} = \begin{bmatrix}
2 & 4 \\
6 & 8
\end{bmatrix}
$$


### Matrix-Vektor-Multiplikation

**Kombinationen**

$$
7\begin{pmatrix}
1 \\
3 \\
5
\end{pmatrix}+8\begin{pmatrix}
2 \\
4 \\
6
\end{pmatrix}=\begin{bmatrix}
1 & 2 \\
3 & 4 \\
5 & 6
\end{bmatrix}\begin{pmatrix}
7 \\
8
\end{pmatrix}=\begin{pmatrix}
23 \\
53 \\
83
\end{pmatrix}\in \mathbb{R}^{3}
$$
**Def 2.4**: Sei 
$$
A=\begin{bmatrix}
| & | & \dots &  | \\
\mathbf{v}_1 & \mathbf{v}_{2} &\dots &  \mathbf{v}_{n} \\
| & | & \dots &  |
\end{bmatrix}\in \mathbb{R}^{m\times n}, \mathbf{x}=\begin{pmatrix}
x_{1} \\
x_{2} \\
\vdots \\
x_{n}
\end{pmatrix}\in \mathbb{R}^{n}
$$
Der Vektor
$$
Ax = \sum_{j=1}^{n}x_{j}v_{j}\in\mathbb{R}^{m}
$$
ist das Produkt von $A$ und $\mathbf{x}$.

**Beobachtung 2.5**:
1. $b\in \mathbb{R}^{m}$ ist eine Linearkombination der Spalten von $A$ $\iff$ es gibt einen Vektor $\mathbf{x}\in \mathbb{R}^{n}$ mit $A\mathbf{x}=b$
2. Die Spalten von A sind linear unabhängig $\iff \mathbf{x}=0$ ist der einzige Vektor mit $A\mathbf{x}=0$

Definition von $A\mathbf{x}$ in Zeilennotation:

### Spaltenraum und Rang

**Def 2.9:** Sei $A$ eine $m\times n$ Matrix. Der Spaltenraum von $A$ ist der Spann der Spalten,
$$
C(A):= \{A\mathbf{x}:\mathbf{x}\in \mathbb{R}^{n}\} \subseteq \mathbb{R}^{m}
$$

