#HS2025 #DM 

Wir haben gesehen: $\langle \mathbb{Z}_{p};\odot_{p}\rangle,\langle \mathbb{Z};+\rangle$, nützliche Eigenschaften.

### Beispiel 1

| \*  | a   | b   | c   |
| --- | --- | --- | --- |
| a   | b   | c   | a   |
| b   | c   | a   | b   |
| c   | a   | b   | c   |

- erfüllt Kommutativität $(\forall x \forall y (x\cdot y=y\cdot x))$
- $c$ linksneutrales Element $(\forall x(c\cdot x=x))$ 
- Assoziativität $(\forall x\forall y\forall z ((x*y)*z)=(x*(y*z)))$
- $x$ neutrales Element $\stackrel{\text{ def.}}\iff x$ linksneutral und rechtsneutral
- Operation: $\oplus_{3}$ 

### Beispiel 2


| \*  | e   | a   | b   | c   |
| --- | --- | --- | --- | --- |
| e   | e   | a   | b   | c   |
| a   | a   | e   | c   | b   |
| b   | b   | c   | e   | a   |
| c   | c   | b   | a   | e   |
- $\mathbb{Z}_{2}\times \mathbb{Z}_{2}, \ e=(0,0),a=(0,1),b=(1,0),c=(1,1)$
- $*=\oplus_{2}\times \oplus_{2}$ 

**Lemma:** $e$ LNE, $e'$ RNE für $\langle S,*\rangle \implies e=e'$

Beweis: 

$$
\begin{align}
e & =e*e' & (e'\text{ RNE}) \\
 & = e'  & (e\text{ LNE})
\end{align}
$$

**Def.:** $\langle S;*,e\rangle$ Monoid, wenn $*$ assoziativ auf $S$ und $e$ neutrales Element.

Beispiele: $\langle \{ 0,1 \}^{*};||,\varepsilon \rangle, \langle \mathbb{Z}_{3};\oplus_{3},0\rangle,\langle \{ 00,01,10,11 \};\text{XOR},00\rangle$

Nachfolgend nur Monoide betrachten.

**Def.:** $b$ Linksinverses von $a \stackrel{\text{ def.}}\iff b*a=e$ (Rechtsinv. $a*b=e$)

$b$ ist ein Inverses von $a\stackrel{\text{ def.}}\iff b$ LI und RI von $a$

**Lemma:** $b$ LI von $a$ und $c$ RI von $a\implies b=c$ 

Beweis: $b=b*e=b*(a*c)=(b*a)*c=e*c=c$ 

**Def.:** $\langle G;*,\hat{\text{ }} ,e\rangle$ Gruppe, falls $\langle G;*,e\rangle$ Monoid und jedes $a\in G$ hat Inverses $\hat{a}.$

Beispiele: $\langle\mathbb{Z}_{3};\oplus_{3},\ominus_{3},0\rangle,\langle\mathbb{Z};+,-(\text{Negation}),0\rangle$ 

Nicht-Beispiel: $\langle \{ 0,1 \}^{*};||,?,\varepsilon\rangle$ 

Frage: $\cancel{\langle \mathbb{Z}_{m},\odot_{m},?,1\rangle},\langle\mathbb{Z}_{7}\setminus \{ 0 \},\odot_{7},\text{mod. Inv.},1\rangle$ 

$\langle\mathbb{Z}_{m};\oplus_{m},\ominus_{m},0\rangle,\langle \mathbb{Q}\setminus\{ 0 \},\cdot, \frac{1}{(\cdot)},1\rangle$

In Gruppe gilt nach Definition
- **G1:** $\forall x\forall y\forall x \ (x*y)*z=x*(y*z)$
- **G2:** $\forall x \ x*e=e*x=x$
- **G2':** $\forall x \ x*e=x$
- **G3:** $\forall x \ x*\hat{x}=\hat{x}*x=e$
- **G3':** $\forall x \ x*\hat{x}=e$

Es gilt: $G_{1}\land G_{2}'\land G_{3}'\vDash G_{2}\land G_{3}$ 

Beweis für $G_{1}\land G_{2}'\land G_{3}'\vDash G_{3}$ 

$$
\begin{align}
\hat{x}*x & =(\hat{x}*x)*e \\
 & =(\hat{x}*x)*(\hat{x}*\hat{\hat{x}}) \\
 & =\hat{x}*((x*\hat{x})*\hat{\hat{x}}) \\
 & =\hat{x}*(e* \hat{\hat{x}}) \\
 & =(\hat{x}*e)* \hat{\hat{x}} \\
 & =\hat{x}* \hat{\hat{x}} =e
\end{align}
$$

**Lemma 5.3:** $\hat{\hat{x}}=x,\quad\widehat{x*y}=\hat{y}*\hat{x},\quad x*y=x*z\implies y=z$

Beweis für $\hat{\hat{x}}=x$: $x=x*e=x*(\hat{x}*\hat{\hat{x}})=(x*\hat{x})*\hat{\hat{x}}=e*\hat{\hat{x}}=\hat{\hat{x}}$ 

Beispiele: $\langle\mathbb{Z}_{2};\oplus_{2},\ominus_{2},0\rangle\times\langle\mathbb{Z}_{2};\oplus_{2},\ominus_{2},0\rangle$

$S_{n}:$ alle Permutationen von $\mathbb{Z}_{n}$, Elemente sind Funktionen $\mathbb{Z}_{n}\to\mathbb{Z}_{n}$ (bijektiv), $*:$ Hintereinanderausführung. 