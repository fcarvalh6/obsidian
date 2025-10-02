#HS2025 #LA 

## Kovektoren und $\mathbf{v}^{T}\mathbf{w}$

Andere Notationen: $<\mathbf{v},\mathbf{w}>, \mathbf{v}^{T}\mathbf{w}$

Wenn $\mathbf{v}$ ein Vektor ist (Spaltenvektor), dann ist $\mathbf{v}^{T}$ ein Kovektor (Zeilenvektor):
$$
\mathbf{v}=\begin{pmatrix}
1 \\
2
\end{pmatrix}, \mathbf{v}^{T}= \begin{pmatrix}
1 & 2
\end{pmatrix}
$$
**Def 1.19** (Kovektor-Vektor-Multiplikation):
$$
\mathbf{v}^{T}\mathbf{w} = \begin{pmatrix}
v_{1} & v_{2} & \dots & v_{m}
\end{pmatrix}\begin{pmatrix}
w_{1} \\
w_{2} \\
\vdots \\
w_{m}
\end{pmatrix}
$$
## Lineare Unabhängigkeit

**Def 1.21:** Vektoren $\mathbf{v_{1}}, \mathbf{v_{2}}, \dots \mathbf{v_{n}}$ sind linear abhängig, falls mindestens einer eine Linearkombination der anderen ist. Andernfalls sind die Vektoren linear unabhängig.

**Alternative Definitionen:** Die folgenden Aussagen sind äquivalent (alle wahr oder alle falsch). 
1. Mindestens einer der Vektoren ist eine Linearkombination der anderen (linear abhängig)
2. Es gibt skalaren $\lambda_{1},\lambda_{2},\dots,\lambda_{n}$ neben $0,0,\dots,0$ so dass $\sum_{j=1}^{n} \lambda_{j} \mathbf{v}_{j} =0$
3. Mindestens einer der Vektoren ist eine Linearkombination der vorherigen Vektoren
## Eindeutigkeit der Linearkombination

Seien $\mathbf{v_{1}}, \mathbf{v_{2}}, \dots \mathbf{v_{n}} \in \mathbb{R}^{m}$ linear unabhängig und seien $w = \sum_{j=1}^{n} \lambda _jv_{j}$ und $w = \sum_{j=1}^{n} \mu_jv_{j}$ zwei Arten, w als Linearkombination zu schreiben, dann gilt: $\lambda_{j}=\mu _j$ für alle $j \in [n]$

## Spann von Vektoren: Menge aller Linearkombinationen

**Def. 1.25:** Seien  $\mathbf{v_{1}}, \mathbf{v_{2}}, \dots \mathbf{v_{n}} \in \mathbb{R}^{m}$. Ihr Spann ist $\text{Span}(\mathbf{v_{1}},\mathbf{v_{2}},\dots,\mathbf{v_{n}}) := \left\{ \sum_{j=1}^{n} \lambda jv_{j}:\lambda j\in \mathbb{R}\;\text{for all}\;j\in[n]\right\}$ 

Es gilt immer: $0 \in \text{Span}(\mathbf{v_{1}}, \mathbf{v_{2}}, \dots \mathbf{v_{n}})$

**Lemma 1.26:** Seien $\mathbf{v_{1}}, \mathbf{v_{2}}, \dots \mathbf{v_{n}} \in \mathbb{R}^{m}$ und sei $\mathbf{v}\in \mathbb{R}^{m}$ eine Linearkombination von $\mathbf{v_{1}}, \mathbf{v_{2}}, \dots \mathbf{v_{n}}$. Dann gilt $$
\text{Span}(\mathbf{v_{1}},\mathbf{v_{2}}, \dots, \mathbf{v_{n}}) = \text{Span}(\mathbf{v_{1}},\mathbf{v_{2}}, \dots, \mathbf{v_{n}},\mathbf{v})
$$