#HS2025 #DM 

## Unterscheidung Allgemeinfall/Interpretation

- Speziell
	- $U=\mathbb{N}$
	- $\forall x(0\leq x)$ (wahr)
	- $\exists x(x\leq 2)\land \exists x (3\leq x)$ (wahr)
	- $\neg(\forall x\;\exists y \quad x < y) \equiv \exists x \neg \exists y \quad x < y\equiv \exists x\;\forall y\quad x\geq y$
- Allgemein
	- $\exists x (F\land G)\vDash (\exists x \;F)\land(\exists x \;G)$
	- $\forall x(F\land G)\equiv (\forall x \;F) \land (\forall x \;G)$
	- $\neg\forall x\; F\equiv \exists x \; \neg F$
	- $\neg \exists x \; F\equiv \forall x\;\neg F$

$\text{prime}(x)\overset{\text{ def}}\iff(x>1) \land \forall y(y|x\to(y=1\lor y=x))$

$y|x\overset{\text{ def}}\iff(y>0)\land(\exists k(y\cdot k=x))$

$\forall x \;(P(x)\to Q(x))\qquad (\forall x\;P(x))\to(\forall x\; Q(x))$ 

## Verwandtschaftsbeziehungen

- $U$ = Menschen (idealisiert)
- $\text{par}(x,y)$
- $\text{child}(x,y)\overset{\text{ def}}\iff \text{par}(y,x)$
- $\text{sibl}(x,y)\overset{\text{ def}}\iff \exists k \; (\text{par}(k,x)\land \text{par}(k,y)\land x\not= y)$
- $\text{grandpar}(x,y)\overset{\text{ def}}\iff \exists k \; \text{child}(k,x)\land \text{par}(k,y)$
- $\text{ancestor}(x,y)\overset{\text{ def}}\iff \text{lässt sich nicht definieren}$

**Allgemeiner:** 
$$
\forall x\ \forall y \ \forall z \; (P(x,y)\land P(y,z))\to P(x,z) \qquad \text{(Transitivität)}
$$
$$
\forall x\ \forall y\ \forall z \; P(x,y)\to P(y,x)\qquad \text{(Symmetrie)}
$$
Was können wir über $\forall x \;P(x)\to\neg(Px)$ sagen?
- erfüllbar, aber keine Tautologie
- $\equiv \forall x \; \neg P(x)$

Schreibweise: $\vDash F$ (F ist allgemeingültig)