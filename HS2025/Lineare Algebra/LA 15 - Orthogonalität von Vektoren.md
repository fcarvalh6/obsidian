#HS2025 #LA 

**Definition 5.1.1:** $\mathbf{v},\mathbf{w}\in \mathbb{R}^{n}$ sind orthogonal, wenn gilt 

$$
\mathbf{v}^{T}\mathbf{w}=\sum_{i=1}^{n}v_{i}w_{i}=0
$$

Sei $V,W$ Unterräume des $\mathbb{R}^{n}$. $V$ und $W$ sind orthogonal, wenn $\forall \mathbf{v}\in V,\mathbf{w}\in W$ gilt:

$$
\mathbf{v}^{T}\mathbf{w}=0
$$

**Lemma 5.1.2:** Seien $\mathbf{v}_{1},\dots,\mathbf{v}_{k}$ Basis des Unterraums $V$ und $\mathbf{w_{1}},\dots,\mathbf{w}_{l}$ Basis des Unterraums $W$. $V,W$ sind orthogonal $\iff$ $\mathbf{v}_{j}$ ist orthogonal zu $\mathbf{w}_{j}$ $\forall i\in \{ 1,\dots,k \},j\in \{ 1,\dots,l \}$

**Lemma 5.1.3:** Seien $V,W$ orthogonale Unterräume des $\mathbb{R}^{n}$ mit Basen $\{ \mathbf{v}_{1},\dots,\mathbf{v}_{k} \}\subseteq V$ und $\{ \mathbf{w}_{1},\dots,\mathbf{w}_{l} \}\subseteq W$. $\{ \mathbf{v}_{1},\dots,\mathbf{v}_{k},\mathbf{w}_{1},\dots,\mathbf{w}_{l} \}$ ist linear unabhängig. 

$||\mathbf{v}||^{2}=0\iff \mathbf{v}=0$

**Korollar 5.1.4:** Seien $V,W$ orthogonale Unterräume des $\mathbb{R}^{n}$. Dann gilt:
1. $V\cap W = \{ 0 \}$
2. $\text{dim}(V)+\text{dim}(W)\le n$
3. Sei (Minkowski-Summe) $V+W=\{ \mathbf{v}+\mathbf{w}\mid \mathbf{v}\in V,\mathbf{w}\in W \}$. $V+W$ ist Unterraum des $\mathbb{R}^{n}$ mit $\text{dim}(V+W)=\text{dim}(V)+\text{dim}(W)$ 

## Beispiele zur Orthogonalität

1. Wenn $\mathbf{v},\mathbf{w}\in \mathbb{R}^{n}$ orthogonal sind, dann gilt $||\mathbf{v}+\mathbf{w}||^{2}=||\mathbf{v}||^{2}+||\mathbf{w}||^{2}$ 
2. $(n=2)$ $\mathbf{v}\not=0,\mathbf{v}=\begin{pmatrix}v_{1} \\ v_{2}\end{pmatrix}$. Sei $\mathbf{w}\in \mathbb{R}^{2}$ orthogonal zu $\mathbf{v}$, d.h. $\mathbf{v}^{T}\mathbf{w}=0$. $\mathbf{v}^{T}\mathbf{w}=0\implies \mathbf{w}=\begin{pmatrix}-v_{2} \\ v_{1}\end{pmatrix}\not=0$. Sei $W=\{ \mu \cdot \mathbf{w}\mid \mu \in \mathbb{R}\}$. $V=\{ \lambda \mathbf{v}\mid \lambda \in \mathbb{R} \}=\{ \mathbf{x}\in \mathbb{R}^{2} \mid \mathbf{w}^{T}\mathbf{x}=0\}$. %

## Orthogonales Komplement eines Unterraums

**Def. 5.1.5:** Sei $V$ Vektorraum des $\mathbb{R}^{n}$. Dann sei $V^{\bot}=\{ \mathbf{x}\in \mathbb{R}^{n}\mid \mathbf{v}^{\top}\mathbf{x}=0 \ \forall \mathbf{v} \in V \}$ das orthogonale Komplement von $V$ . $V^{\bot}$ ist in der Tat Unterraum des $\mathbb{R}^{n}.$

**Theorem 5.1.6:** Sei $A\in \mathbb{R}^{m\times n}$. $N(A)=C(A^{\top})^{\bot}$ 

**Theorem 5.1.7:** Seien $V,W$ orthogonale Unterräume des $\mathbb{R}^{n}$. Folgende Aussagen sind äquivalent:
1. $W=V^{\bot}$
2. $\text{dim}(W)+\text{dim}(V)=n$
3. Jeder Vektor $\mathbf{u}\in \mathbb{R}^{n}$ kann dekomponiert werden als $\mathbf{u}=\mathbf{v}+\mathbf{w},\mathbf{v}\in V,\mathbf{w}\in W$, beide Vektoren eindeutig.