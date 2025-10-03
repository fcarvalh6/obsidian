#HS2025 #LA 

## Spaltenraum und Rang

**Def 2.9:** Sei $A$ eine $m\times n$ Matrix. Der Spaltenraum von $A$ ist der Spann der Spalten.

**Def 2.10:** Sei

$$
A=\begin{bmatrix}
| & | &  & | \\
\mathbf{v}_{1} & \mathbf{v}_{2}  & \dots  & \mathbf{v}_{n} \\
| & | &  & |
\end{bmatrix}
$$

Spalte $\mathbf{v} _j$ ist unabhängig, falls $\mathbf{v} _j$ keine Linearkombination der Spalten $\mathbf{v} _ {1},\mathbf{v} _ {2},\dots,\mathbf{v} _ {j-1}$ ist. Andernfalls ist $\mathbf{v}_ {j}$ abhängig. Der Rang von $A, \: \text{rank}(A)$, ist die Anzahl unabhängiger Spalten.

$\text{rank}(A)=n$: linear unabhängige Spalten

$\text{rank}(A)=0$: Nullmatrix

**Lemma 2.11** (Die unabhängige Spalten erzeugen den Spaltenraum): Sei $A$ eine $m\times n$ Matrix mit $r$ unabhängigen Spalten. Sei $C$ die $m\times r$ Untermatrix von $A$ mit den unabhängigen Spalten. Dann gilt: $\mathbf{C}(C)=\mathbf{C(A)}$.

## Zeilenraum und Transposition

**Def 2.12:** Sei $A= [a_{ij}]_{i=1, j=1}^{m \; n}$ eine $m\times n$ Matrix. Die Transponierte von $A$ ist die $n\times m$ Matrix.
$$
A^{T}:= B := [b_{ij}]_{i=1,j=1}^{n \; m}
$$
mit $b_{ij}=a_{ji}$ für alle $i,j$.

$$
A = \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}\qquad A^{T}=\begin{bmatrix}
1 & 4 \\
2 & 5 \\
3 & 6
\end{bmatrix} 
$$

**Beobachtung 2.13:** $(A^{T})^{T}= A$; $A$ symmetrisch $\iff A^{T}=A$ 

**Def 2.14:** Sei $A$ eine $m\times n$ Matrix. Der Zeilenraum von $A$, $\mathbf{R}(A):=\mathbf{C}(A^{T})$%

**Nullraum:** alles, was zu 0 transformiert wird. 

**2.17:** Sei $A$ eine $m\times n$ Matrix. Der Nullraum von $A$ ist die Menge $N(A)=\{ x\in \mathbb{R}^{n}:Ax=0 \}$.

$\mathbf{0}\in N(A) \quad (A\mathbf{0}=\mathbf{0})$

- $N(A)=\mathbf{0}\iff$ Spalten von A sind linear unabhängig.
- $N(A)=\mathbb{R}^{n}\iff A=\mathbf{0}$
$$
N\left(\begin{bmatrix}
2 & 4 \\
3 & 6
\end{bmatrix}\right) = ? \qquad \begin{bmatrix}
2 & 4 \\
3 & 6
\end{bmatrix}\begin{pmatrix}
x \\
y
\end{pmatrix}=\begin{pmatrix}
0 \\
0
\end{pmatrix} \iff \begin{cases}
2x+4y =0 \\
3x + 6y =0
\end{cases}\iff y={\frac{-x}{2}}
$$

## Matrizen und Lineare Transformationen

**Def 2.18:** Sei $A$ eine $m\times n$-Matrix. Die Funktion $T_{A}:\mathbb{R}^{n}\to \mathbb{R}^{m}, T_{A}: x\mapsto Ax$ ist die Matrixtransformation mit Matrix $A$.
$$
A=\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}: T_{A}:\begin{pmatrix}
x_{1} \\
x_{2}
\end{pmatrix}\mapsto \begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}\begin{pmatrix}
x_{1} \\
x_{2}
\end{pmatrix}=\begin{pmatrix}
x_{2} \\
x_{1}
\end{pmatrix}\in \mathbb{R}^{2}
$$
$$
A=\begin{bmatrix}
1 & 1
\end{bmatrix}:T_{A}:\begin{pmatrix}
x_{1} \\
x_{2}
\end{pmatrix}\mapsto \begin{bmatrix}
1 & 1
\end{bmatrix}\begin{pmatrix}
x_{1} \\
x_{2}
\end{pmatrix}=\begin{pmatrix}
x_{1}+x_{2}
\end{pmatrix}\in \mathbb{R}^{1}
$$

**Geometrische Interpretation:** wie transformiert sich eine Menge von X Eingaben? $A(\text{Ein.}):= \{ Ax : x\in \text{Aus.} \}$. Beispiele im Skript.

**Lemma 2.19:** Sei $A$ eine $m\times n$-Matrix, $x_{1},x_{2}\in \mathbb{R}^{n}, \lambda_{1},\lambda_{2}\in \mathbb{R}$. Dann gilt: $A(\lambda_{1}x_{1}+\lambda_{2}x_{2})=\lambda_{1}Ax_{1}+\lambda_{2}Ax_{2}$.