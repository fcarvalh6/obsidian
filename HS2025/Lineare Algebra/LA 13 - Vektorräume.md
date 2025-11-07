#HS2025 #LA 

## Vektorräume

**Theorem 4.5:** %

**Fakt 4.6:** Sei $(V,+,\cdot)$ ein Vektorraum. $V$ enthält genau einen Nullvektor. 

**Fakt 4.7:** Sei $(V,+,\cdot)$ ein Vektorraum. Für jeden $\mathbf{v}\in V$ gibt es nur einen negativen Vektor $-\mathbf{v}$.

**Definition 4.8:** Sei $V$ ein Vektorraum. Eine nicht-leere Teilmenge $U\subseteq V$ ist ein Unterraum falls es gilt für alle $\mathbf{v},\mathbf{w}\in U$ und $\lambda\in \mathbb{R}$, dass:
1. $\mathbf{v}+\mathbf{w}\in U$
2. $\lambda \mathbf{v}\in U$

**Lemma 4.9:** Sei $U\subseteq V$ ein Unterraum von $V$. Dann $\mathbf{0}\in U$. 

**Lemma 4.11:** Sei $A$ eine $m\times n$ Matrix. Der Spaltenraum $C(A)=\{ A\mathbf{x}:\mathbf{x} \in \mathbb{R}^{n} \}$ ist ein Unterraum von $\mathbb{R}^{n}$. 

**Lemma 4.14:** Sei $V$ ein Vektorraum und sei $U$ Unterraum von $V$. Dann ist $U$ auch ein Vektorraum (mit die gleichen $+,\cdot$ als $V$)

## Basen und Dimension

Basis eines Vektorraums $V$: linear unabhängige Vektoren, die $V$ aufspannen.

**Definition 4.15:** $V$ Vektorraum, $G\subseteq V$ eine (möglicherweise unendliche) Teilmenge. Eine Linearkombination von $G$ ist eine Summe der Form

$$
\sum_{j=1}^{n}\lambda_{j}v_{j}, \ \ F=\{ v_{1},v_{1},\dots,v_{n} \}
$$

endliche Teilmenge von $G$, $\lambda_{1},\lambda_{2},\dots,\lambda_{n}\in \mathbb{R}$.

**Lemma 4.16:** Jede Linearkombination von $V$ ist wieder in $V$.

Beweis: "natürliches Verhalten", das Vektoraddition und Skalarmultiplikation kombiniert. 

$\mathbb{R}[x]$ (Polynome): die unendliche "Linearkombination"

$$
\sum_{j=0}^{\infty}x^{j}\left( =\frac{1}{1-x} \right) \text{ ist kein Polynom.}
$$

**Definition 4.17:** Sei $V$ Vektorraum, $G\subseteq V$.
1. $G$ heisst linear abhängig, wenn es $\mathbf{v}\in G$ gibt, so dass $\mathbf{v}$ Linearkombination von $G\setminus \{ \mathbf{v}\}$
2. Der Spann von $G, \text{ Span}(G)$, ist die Menge aller Linearkombinationen von $G$. 

### Basen

**Def 4.18:** Sei $V$ Vektorraum, $B\subseteq V$ heisst Basis von $V$, wenn $B$ linear unabhängig ist und $\text{Span}(B)=V$ 

Es kann viele Basen geben.

**Beobachtung 4.20:** Jede Menge $B=\{ \mathbf{v_{1}},\mathbf{v_{2}},\dots,\mathbf{v}_{m} \}$ von $m$ linear unabhängigen Vektoren in $\mathbb{R}^{m}$ ist eine Basis von $\mathbb{R}^{m}$.

Hat jeder Vektorraum eine Basis? Ja, wir behandeln nur den "endlich erzeugten Fall".

**Definition 4.21:** $V$ ist endlich erzeugt, wenn es eine endliche Teilmenge $G\subseteq V$ mit $\text{Span}(G)=V$ gibt.

$\mathbb{R}^{m}$ ist endlich erzeugt.

$\mathbb{R}[x]$ ist nicht endlich erzeugt.

**Das Austauschlemma von Steinitz:** Luxusversion von Lemma 1.28. %

**Theorem 4.24:** Sei $V$ endlich erzeugt und $B,B'$ zwei Basen von $V$. Dann gilt $|B|=|B'|.$ 

### Dimension

**Definition 4.25:** Sei $V$ endlich erzeugt. Dann ist die Dimension von $V$, $\text{dim}(V)$, die Grösse einer beliebigen Basis von $V$. 
