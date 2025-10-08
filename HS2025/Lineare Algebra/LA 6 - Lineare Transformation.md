#HS2025 #LA 

## Lineare Transformation

**Def. 2.21** Eine Funktion T: $\mathbb{R}^{n}\to\mathbb{R}^{m}$ / $\mathbb{R}^{n}\to\mathbb{R}$ heisst lineare Transformation/ lineares Funktional, falls das folgende Linearitäts-Axiom für alle $\mathbf{x}_{1},\mathbf{x}_{2} \in \mathbb{R}^{n}$ und alle $\lambda\in \mathbb{R}$ gilt: 

$$
T(\lambda_{1}\mathbf{x}_{1}+\lambda_{2}\mathbf{x}_{2})=\lambda_{1}T(\mathbf{x}_{1}) + \lambda_{2}T(\mathbf{x}_{2}).
$$

Dasselbe kann alternativ mit zwei Axiomen gesagt werden (Lemma 2.23): für alle $\mathbf{x},\mathbf{x}'\in \mathbb{R}^{n}$ und alle $\lambda\in \mathbb{R}:$

$$
\begin{align}
&(\text{i}) & T(\mathbf{x}+\mathbf{x}') = T(\mathbf{x}) + T(\mathbf{x}') \; \text{und}\\
&(\text{ii}) & T(\lambda \mathbf{x}) = \lambda T(\mathbf{x})
\end{align}
$$

**Beobachtung 2.22:** Jede Matrixtransformation $T _ {A}$ ist eine lineare Transformation. 

**Beispiele:**
1. Sei $\mathbf{v}\in \mathbb{R}^{m}. \; T:\mathbb{R}^{m}\to\mathbb{R},\quad T: \mathbf{x} \mapsto \sum_{i=1}^mv_{i}x_{i} =\mathbf{v}^{T}\mathbf{x}$ ist ein lineares Funktional (der Kovektor $\mathbf{v}$; siehe Def. 1.20). Zum Beweis, prüfe (i), (ii):

$$
\begin{align}
&(i) &T(\mathbf{x}+\mathbf{x}') = \sum_{i=1}^m v_{i}(x_{i}+x'_{i}) = \sum_{i=1}^m v_{i}x_{i}+\sum_{i=1}^mv_{1}x'_{i} = T(x)+T(x') \\
&(ii) &T(\lambda \mathbf{x}) = \sum_{i=1}^mv_{i}(\lambda x_{i}) = \lambda \sum_{i=1}^m v_{i}x_{i} = \lambda T(x)
\end{align}
$$

2. $T: \mathbb{R}^{3}\to\mathbb{R}^{2},\quad T:\mathbf{x}\mapsto \begin{pmatrix}x_{1}+2x_{2} \\ 3x_{2}+4x_{2}\end{pmatrix}$ ist eine lineare Transformation. Zum Beweis beobachten wir $T = T_{A}$ für

$$
A=\begin{bmatrix}
1  & 2 & 0 \\
0 & 3 & 4
\end{bmatrix} : T_{A}(\mathbf{x}) = A\mathbf{x}=\begin{bmatrix}
1 & 2 & 0 \\
0 & 3 & 4
\end{bmatrix}\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{pmatrix}=\begin{pmatrix}
1\cdot x_{1}+2\cdot x_{2}+0\cdot x_{3} \\
0\cdot x_{1}+3\cdot x_{2}+4\cdot x_{3}
\end{pmatrix}
$$

nun benutze Beobachtung 2.22 (jede Matrixtransformation ist eine lineare Transformation).

3. $T:\mathbb{R}^{n}\to\mathbb{R}^{m}, \mathbf{x}\mapsto 0$ ist eine lineare Transformation ($T = T_{A}$ für $A=\mathbf{0}$)

4. $T: \mathbb{R}^{m}\to\mathbb{R}^{m}, \mathbf{x}\mapsto \mathbf{x}$ ist eine lineare Transformation ($T=T_{A}$ für $A = \mathbf{I}$)

5. $T: \mathbb{R}^{m}\to \mathbb{R},\; T: \mathbf{x}\mapsto \sum_{i=1}^m |x_{i}|=||x||_{1}\;\text{(1-norm)}$ ist **kein** lineares Funktional. Wenn $\mathbf{x}\not= 0$ und $\lambda<0$, dann $T(\lambda \mathbf{x})>0$, aber, $\lambda T(\mathbf{x})<0$: (ii) geht schief.

6. $T:\mathbb{R}^{n}\to\mathbb{R}^{m},\; \mathbf{x}\mapsto \mathbf{v}\not=\mathbf{0}$ ist keine lineare Transformation: (i) $\underbrace{T(\mathbf{x}+\mathbf{x}')}_{\mathbf{v}} = \underbrace{T(\mathbf{x})+T(\mathbf{x'})}_{2\mathbf{v}}$
**Lemma 2.24:** Sei $T:\mathbb{R}^{n}\to\mathbb{R}^{m}$ / $T:\mathbb{R}^{n}\to\mathbb{R}$ eine lineare Transformation / lineares Funktional. Dann gilt $T(\mathbf{0})=\mathbf{0}$ / $T(\mathbf{0})=0$. Beweis:

$$
T(\mathbf{0})=T(\mathbf{0}\cdot \mathbf{x}) = \mathbf{0}\cdot T(\mathbf{x}) = \mathbf{0}
$$

**Lemma 2.25:** Sei $T:\mathbb{R}^{n}\to\mathbb{R}^{m}$ / $T:\mathbb{R}^{n}\to\mathbb{R}$ eine lineare Transformation / ein lineares Funktional. Seien $\mathbf{x}_{1}, \mathbf{x_{2}},\dots,\mathbf{x}_{l} \in \mathbb{R}^{n}$ und $\lambda_{1},\lambda_{2},\dots,\lambda_{l}\in \mathbb{R}$. Dann gilt: 

$$
T\left( \sum_{j=1}^l\lambda_{j}\mathbf{x}_{j} \right)=\sum_{j=1}^l\lambda _{j} T(x_{j}).
$$

- $l=2:$ Definition 2.21
- $l=0:$ Lemma 2.24
- $l=1:$ (ii)
- $l>2:$ 

Beweis:

$$
\begin{align}
T\left( \sum_{j=1}^l \lambda_{j}\mathbf{x}_{j} \right) = & T\left( \sum_{j=1}^{l-1}\lambda_{j}\mathbf{x}_{j}+\lambda_{l}\mathbf{x}_{l} \right)\\ \\
= & T\left( \sum _{j=1}^{l-1} \lambda_{j}\mathbf{x}_{j}\right)+\lambda_{l}T(\mathbf{x}_{l})\\ \\
\text{Wiederhole für }l-2,\dots,1
\end{align}
$$

Beweis per Induktion (ohne Pünktchen wie in "Wiederhole für ... "):

Für $l=0:$ direkter Beweis (Basisfall), Lemma (2.24)

Für $l>0,$ mache den Induktionsschritt: wenn die Aussage für $l-1$ gilt, dann auch für $l$. Dann wissen wir: Aussage gilt für alle $l$. 

Induktionsschritt:

$$
\begin{align}
T\left( \sum_{j=1}^l\lambda_{j}\mathbf{x}_{j} \right) = &  T\left( \sum_{j=1}^{l-1} \lambda_{j}\mathbf{x}_{j}+\lambda_{l}\mathbf{x}_{l}\right)\\ \\
=& T\left( \sum_{j=1}^{l-1} \lambda_{j}\mathbf{x}_{j}\right) +\lambda_{l}T(\mathbf{x}_{l})\\ \\
=& \sum_{j=1}^{l-1}\lambda_{j}T(\mathbf{x}_{j}) + \lambda_{l}T(\mathbf{x}_{l})\\ \\
=& \sum_{j=1}^l \lambda_{j}T(\mathbf{x}_{j})
\end{align}
$$


