#HS2025 #LA 

## Zusammenfassung

Sei $V$ Unterraum des $\mathbb{R}^{n}$. 
- $V^{\bot}=\{ \mathbf{x}\in \mathbb{R}^{n}\mid \mathbf{v}^{\top}\mathbf{x}=0 \ \forall \mathbf{v}\in V \}$.
- Theorem 5.1.7 $\implies$ $\mathbb{R}^{n}=V+V^{\bot}=V^{\bot}+(V^{\bot})^{\bot}$
- $\implies V = (V^{\bot})^{\bot}$ 
- Basis von $V$ "plus" Basis von $V^{\bot}$ = Basis des $\mathbb{R}^{n}$  

**Wichtigste Beispiel:**

Sei $A\in \mathbb{R}^{m\times n}$

$N(A)=C(A^{\top})^{\bot}$ mit $N(A)^{\bot}=C(A^{\top})$

**Lemma 5.1.10:** Sei $A\in \mathbb{R}^{m\times n}$, $N(A)=N(A^{\top}A)$ 

## Projektion

**Idee:** Angenommen $A\mathbf{x}=\mathbf{b}$ nicht lösbar.

Finde ein Vektor $\hat{\mathbf{x}}$ mit $A \hat{\mathbf{x}}$ relativ nah an $\mathbf{b}$.

**Definition:** gegeben Unterraum $S \subseteq \mathbb{R}^{m}$ und $\mathbf{b}\in \mathbb{R}^{m}$ %

**Spezialfall:** $S$ ist eindimensionaler Unterraum des $\mathbb{R}^{n}$, d.h. $S=\{ \lambda a \mid \lambda\in \mathbb{R} \}$ und $a\in \mathbb{R}^{m},a\not=0$ gegeben.

Gegeben $b\in \mathbb{R}^{m}$, $\operatorname{proj}_{S}(b)=\lambda^{*}\cdot a$, mit $\lambda^{*}\in \mathbb{R}$ und $b-\operatorname{proj}_{S}(b)$ orthogonal zu $\operatorname{proj}_{S}(b)$. 

**Lemma 5.2.2** 