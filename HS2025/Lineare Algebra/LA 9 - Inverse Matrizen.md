#HS2025 #LA 

**Def. 2.48:** Seien $X,Y$ Mengen, $f:x\to y$ eine Funktion
1. $f$ ist injektiv, fall es für jedes $y\in Y$ höchstens ein $x\in X$ mit $f(x)=y$ gibt. 
2. $f$ ist surjektiv, fall es für jedes $y\in Y$ mindestens ein $x\in X$ mit $f(x)=y$ gibt.
3. $f$ ist bijektiv (umkehrbar), wenn $f$ injektiv und surjektiv ist. 
4. Die Inverse (Umkehrfunktion) einer bijektiven Funktion $f$ ist die Funktion $f^{-1}:y\to x, y\mapsto$ das eindeutige $x \in X$ mit $f(x)=y$.

**Fakt 2.49:** Wenn $f:x\to y$ bijektiv ist, dann ist $f^{-1}:y\to x$ bijektiv und $(f^{-1})^{-1}=f$.

Ausserdem: $f^{-1}\circ f=\text{id}, \text{id}: \text{Eingabe}\mapsto \text{Eingabe}$.

Matrixtransformation $T_{A}:\mathbb{R}^{n}\to \mathbb{R}^{m}, \mathbf{x}\mapsto A\mathbf{x}$
- $m<n \quad (A \text{ breit}):$ nicht injektiv
	- Intuition: Mehr Eingaben als mögliche Ausgaben
- $m>n \quad (A \text{ hoch}):$ nicht surjektiv
	- Intuition: Mehr mögliche Ausgaben als Eingaben
-  $m=n \quad (A \text{ quadratisch}):$ potenziell bijektiv, aber nicht immer (siehe $A=\mathbf{0}\in \mathbb{R}^{m\times n}$).

**Lemma 2.52:** Sei $T:\mathbb{R}^{m}\to\mathbb{R}^{m}$ eine bijektive lineare Transformation. Dann ist die Inverse $T^{-1}:\mathbb{R}^{m}\to\mathbb{R}^{m}$ auch eine lineare Transformation (und bijektiv nach Fakt 2.49).

Beweis: Zeige Linearität von $T^{-1}$:

$$
x_{1}:=T^{-1}(y_{1}), x_{2}:=T^{-1}(y_{2}) \quad(T(x_{1})=y_{1},T(x_{2})=y_{2}
$$

$$
\begin{align} \\
T^{-1}(\lambda_{1}y_{1}+\lambda_{2}y_{2}) & =\lambda T^{-1}(y_{1})+ \lambda_{2}T^{-1}(y_{2}) \\
 & = \lambda_{1}x_{1}+\lambda_{2}y_{2}
\end{align}
$$
%^

Wende $T^{-1}$ auf beiden Seiten an:

$$
T^{-1}(T(\lambda_{1}T^{-1}(y_{1})+\lambda_{2}T^{-1}(y_{2}))) = T^{-1}(\lambda_{1}y_{1}+\lambda_{2}y_{2})
$$

**Lemma 2.53:** Sei $A$ eine $m\times m$ Matrix. Die folgenden drei Bedingungen sind äquivalent:
1. $T_{A}:\mathbb{R}^{m}\to\mathbb{R}^{m}$ ist bijektiv.
2. Es gibt eine $m\times m$ Matrix $B$ mit $BA=I$.
3. Die Spalten von $A$ sind linear unabhängig.

Beweisstruktur: $1.\implies 2. \implies 3. \implies 1.$

Beweis:

$1. \implies 2.$ 

Wenn $T_{A}$ bijektiv ist, ist die Inverse $T_{A}^{-1}$ eine Matrixtransformation $T_{B}:T_{A}$ ist lineare Transformation (Beobachtung 2.22), also ist $T_{A}^{-1}$ auch eine lineare Transformation (Lemma 2.52) und somit eine Matrixtransformation (Theorem 2.26). Nach Fakt 2.49: $T_{B}\circ T_{A} = \text{id} = T_{BA}$. Nach Theorem 2.26 (eindeutige Matrix): $BA = I$

$2. \implies 3.$ 

Wenn $BA = I$, dann ist $\mathbf{x}=\mathbf{0}$ der einzige Vektor mit $A\mathbf{x}=\mathbf{0}$ (also hat $A$ linear unabhängige Spalten, Beobachtung 2.5): Sei $A\mathbf{x}=\mathbf{0}$. Dann gilt $\mathbf{x}=(BA)\mathbf{x}=B(A\mathbf{x})=B\mathbf{0}=\mathbf{0}$.

$3. \implies 1.$ Wenn die Spalten von $A$ linear unabhängig sind, ist $T_{A}$ Surjektiv: für jedes $\mathbf{y}\in \mathbb{R}^{m}$ gibt es ein $\mathbf{x}\in \mathbb{R}^{m}$ mit $T_{A}(\mathbf{x})=A\mathbf{x} = \mathbf{y}$. Das stimmt, weil die Spalten von $A$ $\mathbb{R}^{m}$ aufspannen (Lemma 1.28). $T_{A}$ ist sogar bijektiv, weil $\mathbf{y}$ in eindeutiger Weise als Linearkombination der Spalten von $A$ geschrieben werden kann (Lemma 1.24). 

In $2.$ hätten wir auch $AB=I$ sagen können:

**Lemma 2.54:** Seien $A,B$ $m\times m$ Matrizen mit $BA=I$. Dann gilt auch $AB=I$.

### Definitionen und Eigenschaften

**Def 2.55** Eine $m\times m$ Matrix $A$ heisst invertierbar, wenn es eine $m\times m$ Matrix $B$ mit $BA=I$ gibt. (Nach Lemma 2.53 ist das äquivalent dazu, dass $A$ linear unabhängige Spalten hat). Andernfalls heisst $A$ singulär. 

**Beob. 2.56:** Wie hätten auch $AB=I$ oder $AB=BA=I$ sagen können (Lemma 2.54).

Beweis: Seien $B,B'$ zwei Matrizen, die die Eigenschaften haben. Dann gilt $B=B':$

$$
B=IB=(B'A)B=B'(AB) = B'
$$

**Def. 2.57:** Sei $A$ eine $m\times m$ Matrix. $A$ ist genau dann investierbar, wenn es eine $m\times m$ Matrix $B$ mit $BA=I$ (oder $AB=I$, oder $AB=BA=I$) gibt. In diesem Fall ist $B$ eindeutig und heisst die Inverse von $A$.

**Beob. 2.58:** $(A^{-1})^{-1}=A$ (insbesondere ist $A^{-1}$ invertierbar).

Fall $1\times 1$:

$$
A=[a]\implies A^{-1}=\left[ \frac{1}{a} \right] \quad (\text{falls }a\not=0)
$$

Fall $2\times 2$:

$$
A=\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}\implies A^{-1}=\frac{1}{ad-bc}\begin{bmatrix}
d & -b \\
-c & a
\end{bmatrix}\quad (\text{falls }ad-bc \not=0)\iff \begin{pmatrix}
a \\
c
\end{pmatrix},\begin{pmatrix}
b \\
c
\end{pmatrix} \text{ lin. unab.}
$$

**Lemma 2.59:** $(AB)^{-1}=B^{-1}A^{-1}$

Beweis: Prüfe eine der Eigenschaften

$$
(B^{-1}A^{-1})(AB)=B^{-1}(A^{-1}A)B = BIB^{-1}=B^{-1}B=I
$$

**Lemma 2.60:** $(A^{T})^{-1}=(A^{-1})^{T}$.

