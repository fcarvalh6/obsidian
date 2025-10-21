#HS2025 #LA 

(Gemischte) Produkte (z.B. $\mathbf{x}^TA^TA\mathbf{x}$) können ausgewertet werden, als wären:
- Vektoren in $\mathbb{R}^{m}$  $m\times 1$-Matrizen
- Kovektoren in $(\mathbb{R^{m}})^T$  $1\times m$-Matrizen
- Skalare in $\mathbb{R}$  $1\times 1$-Matrizen

Assoziativität gilt immer noch, Klammerung egal.

Transposition eines Produkts: transponiere individuelle Faktoren und multipliziere sie in umgekehrter Reihenfolge. 

Beispiele:

$$
\begin{align}
\underbrace{\underbrace{\mathbf{x}^TA^T}_{Kovektor}\underbrace{A\mathbf{x}}_{Vektor}}_{Skalar} = (A\mathbf{x})^{T}A\mathbf{x}=||A\mathbf{x||^2} \\
\text{Alternative Klammerung: }\mathbf{x}^TA^TA\mathbf{x} 
\end{align}
$$

$$
\underbrace{\mathbf{v}^T\mathbf{w}}_{\text{Skalar}}\underbrace{\mathbf{v}^T\mathbf{w}}_{\text{ Skalar}} = (\mathbf{v}^T\mathbf{w})^{2}\qquad \underbrace{\mathbf{v}^T}_{\text{Kovektor}}\underbrace{(\mathbf{w}\mathbf{v}^{T})\mathbf{w}}_{\text{ Matrix}\cdot \text{Vektor}}
$$

Effizienteste Klammerung kann mit dynamischer Programmierung ausgeführt werden.

**Def. 2.45:**

$$
\begin{bmatrix}
-  & \mathbf{u}_{1}^T & - \\
- & \mathbf{u}_{2}^T & - \\
 & \vdots &  \\
- & \mathbf{u}_{A}^T & -
\end{bmatrix}B=\begin{bmatrix}
-  & \mathbf{u}_{1}^TB & - \\
- & \mathbf{u}_{2}^TB & - \\
 & \vdots &  \\
- & \mathbf{u}_{A}^TB & -
\end{bmatrix}
$$

**CR-Zerlegung:** 

Primfaktorzerlegung, z.B. $1001=7\cdot 11 \cdot 13$

Matrixzerlegung: schreibe $A$ als Produkt anderer Matrizen, um $A$ besser zu verstehen.

**Theorem 2.46:** Sei $A$ eine $m\times n$ Matrix mit Rang $r$ (Def. 2.10). Sei $C$ die $m\times r$ Untermatrix mit den unabhängigen Spalten. Dann gibt es eine eindeutige $r\times n$ Matrix $R'$ mit $A=CR'$ 

Beispiel ($r=1$):

$$
\begin{bmatrix}
2 & 4 & 6 \\
3 & 6 & 9
\end{bmatrix}=\begin{bmatrix}
2 \\
3
\end{bmatrix}\begin{bmatrix}
1 & 2 & 3
\end{bmatrix}
$$

Spalten von $R'$: Skalare, um jede Spalte von $A$ als skalares vielfaches der ersten Spalten zu schreiben. 

Beweis: $A$ und $C$ haben den gleichen Spaltenraum (Lemma 2.11) $\implies$ jede Spalte von A ist eine Linearkombination der Spalten von $C$:

$$
\mathbf{v}_{j} = C \mathbf{x_{j}} , \mathbf{x}_{j} = \text{Vektor von x Skalaren} : \begin{bmatrix}
| & | &  & | \\
\mathbf{v}_{1} & \mathbf{v}_{2} & \dots & \mathbf{v}_{n} \\
| & | &  & |
\end{bmatrix}=C\begin{bmatrix}
| & | &  & | \\
\mathbf{x}_{1} & \mathbf{x}_{2} & \dots & \mathbf{x}_{n} \\
| & | &  & |
\end{bmatrix}
$$

Die Spalten von $C$ sind linear unabhängig, d.h. alle $\mathbf{x}_{j}$ sind eindeutig (Lemma 1.24). Also ist $R'$ eindeutig.

Wir haben die Existenz der CR-Zerlegung bewiesen, nicht aber ihre effiziente Berechnung (siehe Kapitel 3).

$A=CR'$ und Matrixkompression
- $m\times n$ Matrix $A$: $m\cdot n$ Einträge
- $m\times n$ Matrix $A$ mit Rang $r$:
	- $C$ hat $m\cdot r$ Einträge
	- $R'$ hat $r\cdot n$ Einträge
	- insgesamt $(m+n)\cdot r$ Einträge

Wenn $r$ klein ist: Speicherung/Übertragung von $C$ und $R'$ statt $A$ ist effizienter.

$A\mathbf{x}=CR'\mathbf{x}=C(R'\mathbf{x})$

$AB=CR'B=C(R'B)$

Invertierbare und inverse Matrizen (Abschnitt 2.4)

$T_{A}:\text{Eingabe }\mapsto\text{Ausgabe ("do")} \quad \mathbf{x}\mapsto A\mathbf{x}$

$?:\text{Ausgabe }\mapsto\text{Eingabe ("undo")}$

$A=\mathbf{0}:T_{A}:\text{Eingabe }\mapsto \mathbf{0}$ "undo" geht nicht (wir wissen nicht, was die Eingabe war)