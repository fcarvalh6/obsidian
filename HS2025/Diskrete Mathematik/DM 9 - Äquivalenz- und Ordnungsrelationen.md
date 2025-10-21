#HS2025 #DM 

## Äquivalenzrelationen

**Def.** $\rho* \overset{\text{def}}=\bigcup \mathcal{P}_{\rho}$ mit $\mathcal{P}_{\rho}=\{ \rho,\rho^{2},\rho^{3},\dots \}$

Beispiel: $\text{parent}* =\text{ancestor}$

**Def.** $\rho \text{ ÄR} \overset{\text{ def}}\iff \rho\text{ reflexiv, symmetrisch, transitiv}$

Beispiel: $\text{id}=\{ (a,a)\mid a\in A \}, \; \equiv_{m}, \; \{ A=\text{Menschen}, a\; \rho \; b \}\overset{\text{ def}}\iff\text{a und b sind gleich alt}$

**Def.** Äquivalenzklasse: $[a]_{\theta}=\{ b\in A \mid b \;\theta \;a \}$

Beispiel: $A=\mathbb{Z}, \theta = \equiv_{5}, [0]_{\theta}=\{ 0,-5,5,-10,10,\dots \}$, $[2]_{\theta}=\{ 2,-3,7,-8,12\dots \}$, $[5]_{\theta}=[0]_{\theta}$

**Def.** $A / \theta = \{ [a]_{\theta} \mid a\in A \}$ ist Quotientenmenge von $A$ nach $\theta$. Äquivalentklassen bilden Partition von A ($[a]_{\theta}=[b]_{\theta}$ oder $[a]_{\theta}\cap [b]_{\theta}=\varnothing$ und $A=\bigcup A / \theta$)

## Betrachte

$A = \mathbb{Z}\times(\mathbb{Z} / \{ 0 \})$ und $\sim$ mit $(a,b)\sim (c,d)\overset{\text{ def}}\iff a\cdot d=b\cdot c$

**Lemma:** "$\sim$" ist ÄR.

Beweis:
1. "~" ist reflexiv: $(a,b)$~$(a,b)\dot\iff a\cdot b = b \cdot a\dot\iff ab=ab$ wahr
2. "~" ist symmetrisch: $(a,b)$~$(c,d)\dot\iff ad=bc\dot\iff bc=ad\dot\iff cb=da \dot\iff(c,d)$~$(a,b)$
3. "~" ist transitiv: $(a,b)$~$(c,d)$, $(c,d)$~$(e,f)\dot\implies ad=bc$ und $cf=de$ 
	1. Wenn $c=0$, dann $a=0$ und $e=0$ $\dot\implies af=be\dot\implies(a,b)$~$(e,f)$
	2. Wenn $c\not=0$, dann $adcf=bcde\dot\implies adf=bde\dot\implies af=be\dot\iff (a,b)$~$(e,f)$

## Rationale Zahlen

$\mathbb{Q}\overset{\text{def}}=(\mathbb{Z}\times(\mathbb{Z\setminus \{ 0 \}})) /$~ 

$[(2,7)]_{\sim}=\{ (4,14),(6,21),\dots \}=\frac{2}{7}$

**Bemerkung:** Schnitt von $\text{ÄR}$ ist wieder $\text{ÄR}$.

Beispiel: $\equiv_{3}\cap\equiv_{5} \;=\; \equiv_{15}$ 

## Ordnungsrelation

**Eigenschaften:** reflexiv, antisymmetrisch, transitiv

Beispiel: $A=\mathbb{Z}$, Relation $\preccurlyeq\;=\;\leq$, nicht-Beispiel: $\preccurlyeq\;=\;<$ 

**Definition:** $< \;\overset{\text{def}}=\; \preccurlyeq \setminus \text{ id}$

Beispiel: $A=\mathbb{N}\setminus \{ 0 \}, \preccurlyeq=1$ (Teilbarkeit 1)

Beispiel: $A=\mathcal{P}(B), \preccurlyeq \; = \; \subseteq$

$(A, \preccurlyeq)$ nennt man auch poset

Beispiel: Wenn ($A;\preccurlyeq$) poset, ist $\prec$ transitiv?

Beweis: Sei $a \prec b,b\prec c$, zu zeigen: $a \prec c$

%
