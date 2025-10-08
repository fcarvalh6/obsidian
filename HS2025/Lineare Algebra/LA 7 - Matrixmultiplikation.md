#HS2025 #LA 

## Die Matrix einer linearen Transformation

**Theorem 2.26:** Sei $T:\mathbb{R}^{n}\to\mathbb{R}^{m}$ eine lineare Transformation. Es gibt eine eindeutige $m\times n$ Matrix $A$ sodass $T=T_{A}$.

Beweis: für $T=T_{A}$ brauchen wir insbesondere $T(e_{j}) = T_{A}(e_{j})=Ae_{j}\text{ (Spalte j von A)}$. Die einzige Kandidatin für $A$ ist

$$
A=\begin{bmatrix}
| & | &  & | \\
T(e_{1}) & T(e_{2}) & \dots & T(e_{n}) \\
| & | &  & |
\end{bmatrix}
$$

Diese $A$ tut es für alle $\mathbf{x}$ ($T(\mathbf{x})=T_{A}(\mathbf{x})$ für alle $\mathbf{x}$)

$$
\begin{align}
T_{A}(\mathbf{x})=& A\mathbf{x} \\
= & \sum_{j=1}^n x_{j} T(e_{j}) &(\text{Def. 2.4}) \\
=  & T\left( \sum_{j=1}^n x_{j}e_{j} \right) & (\text{Lemma 2.25}) \\
= & T(\mathbf{x}), \text{wie in }\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{pmatrix}=x_{1}\begin{pmatrix}
1 \\
0 \\
0
\end{pmatrix}+x_{2}\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}+x_{3}\begin{pmatrix}
0 \\
0 \\
1
\end{pmatrix}
\end{align}
$$
**Folgerung:** wenn wir für eine lineare Transformation $T$ die Werte $T(e_{1}), T(e_{2}),\dots,T(e_{n})$ kenne, dann kennen wir $A$ und $T(\mathbf{x})$ für alle $\mathbf{x}$.

## Matrixmultiplikation 

Die Kombination zweier Matrixtransformationen ist wieder eine Matrixtransformation.

**Definition 2.33 (Komposition von Funktionen):** Seien $g:x\to y$ und $f:y\to z$ zwei Funktionen. Die Funktion $h: x\to f(g(x))$ ist die Komposition von $f$ und $g$, geschrieben als $h=f \circ g$ ("wende erst $g$ an, dann $f$!")

**Lemma 2.34:** Seien $T_{B}:\mathbb{R}^{b}\to \mathbb{R}^{n}$ und $T_{A}:\mathbb{R}^{n}\to\mathbb{R}^{a}$ zwei Matrixtransformationen, die Komposition $T_{A}\circ T_{B}:\mathbb{R}^{b}\to \mathbb{R}^{a}$ ("erst $T_{B}$, dann $T_{A}$") ist auch eine Matrixtransformation.

Beweis:
1. $T_{A}\circ T_{B}$ ist eine lineare Transformation. (Def. 2.21)

$$
\begin{align}
T_{A}\circ T_{B}(\lambda_{1}x_{1}+\lambda_{2}x_{2}) \\
=  & T_{A}(T_{B}(\lambda_{1}x_{1}+\lambda_{2}x_{2}))  & (\text{Komposition}) \\
= & T_{A}(\lambda_{1}T_{B}(x_{1})+\lambda_{2}T_{B}(x_{2})) & (\text{Linearität von }T_{B}) \\
= & \lambda_{1}T_{A}(T_{B}(x_{1})) + \lambda_{2}T_{A}(T_{B}(x_{2})) & (\text{Linearität von }T_{A}) \\
= & \lambda_{1}(T_{A}\circ T_{B})(x_{1})+\lambda_{2}(T_{A}\circ T_{B})(x_{2}) & (\text{Komposition}) \\
\end{align}
$$

2. $T_{A}\circ T_{B}$ ist eine Matrixtransformation nach Lemma 2.25

Was ist die Matrix von $T_{A}\circ T_{B}$?

**Lemma 2.35:** Sei $A$ eine $a\times n$ Matrix ($T_{A}:\mathbb{R}^{n}\to\mathbb{R}^{a}$) und $B=\begin{bmatrix}| & | &  & | \\ \mathbf{x}_{1} & \mathbf{x}_{2} & \dots & \mathbf{x}_{n} \\ | & | &  & |\end{bmatrix}$ eine $n\times b$ Matrix ($T_{B}: \mathbb{R}^{b}\to\mathbb{R}^{n}$). Die $a\times b$ Matrix ($T_{A}\circ T_{B}: \mathbb{R}^{b}\to \mathbb{R}^{a}$)

$$
C=\begin{bmatrix}
| & | &  & | \\
A\mathbf{x}_{1} & A\mathbf{x}_{2} & \dots & A\mathbf{x}_{b} \\
| & | &  & |
\end{bmatrix}
$$

ist die eindeutige Matrix mit $T_{C}=T_{A} \circ T_{B}$.

Beweis: $T_{C}$ und $T_{A}\circ T_{B}$ müssen auf den Standardeinheitsvektoren dasselbe tun:

$$
\begin{align}
\underbrace{T_{C}(e_{j})}_{Ce_{j, \text{ Spalte }j \text{ von C}}}=(T_{A}\circ T_{B})(e_{j}) = & T_{A}(T_{B}(e_{j})) \\
= & A \underbrace{ T_{B}(e_{j})}_{Be_{j, \text{ Spalte } j \text{ von }B}}
\end{align}
$$

"Spalte $j$ von $C$ ist $A\mathbf{x}_{j}$"

$C$ ist die einzige , und da es eine Matrix gibt, ist $C$ diese Matrix.

**Definition 2.36 (Matrixmultiplikation in Spaltennotation):** Sei $A$ eine $a\times n$ Matrix und $B=\begin{bmatrix}| & | &  & | \\ \mathbf{x}_{1} & \mathbf{x}_{2} & \dots & \mathbf{x}_{b} \\ | & | &  & |\end{bmatrix}$ eine $n\times b$. Die $a\times b$ Matrix $AB=\begin{bmatrix}| & | &  & | \\ A\mathbf{x}_{1} & A\mathbf{x}_{2} & \dots & A\mathbf{x}_{b} \\ | & | &  & |\end{bmatrix}$ ist das Produkt von $A$ und $B$.

**Korollar 2.37:** $T_{A} \circ T_{B}=T_{AB}$

Übliche Definition von $AB$: "Zeilen von $A$ mal Spalten von $B$".

**Beobachtung 2.38:** Sei %

**Korollar 2.41:** Sei $I$ die $m\times n$ Identitätsmatrix. Dann gilt $IA=A$ für alle $n\times n$ Matrizen $A$ und $AI=A$ für alle $n\times m$ Matrizen $A$.

**Lemma 2.40:** $(AB)^T = B^TA^T$.

## Distributivität und Assoziativität

**Lemma 2.42:**
1. $A(B+C)=AB+AC, (A+B)C=AC+BC\qquad\text{Distributivität}$
2. $(AB)C=A(BC)\qquad\text{Assoziativität}$

Beweis: Nach Korollar 2.37:
- $(AB)C$ ist die Matrix von $(T_{A}\circ T_{B})\circ T_{C}$
- $A(BC)$ ist die Matrix von $T_{A} \circ (T_{B}\circ T_{C})$

Das sind die gleichen Transformationen und haben deshalb die gleichen Matrizen $(AB)C = A(BC)$ (Theorem 2.26)

Funktioniert auch für mehr Matrizen (verallgemeinerte Assoziativität)