#FS2026 #A 

### Quantifiers
- $\forall$ "for all"
- $\exists$ "exists"
- $\exists !$ "exists exactly one"
- $\not\exists$ "exists none"

### Logic
- $\land$ "and"
- $\lor$ "or (inclusive)"
- $\implies$ "implication"
- $\iff$ "equivalence"

### Sets
- $X\subset Y \iff (\forall x \in X : x \in X \implies x \in Y)$ (subset)
- $X\subsetneq Y \iff (X \subset Y)\land (X\not= Y)$ (non-trivial subset)
- Let $X \subset Y$, then $X^{C}:=\{ y \mid y \in Y \land y \not \in X \}$ (complement)
- $\cup \ \cap \  \setminus \ \times$  (union, intersection, difference, cartesian product)

### Intervals
- $(a,b)$ (open)
- $[a,b]$ (closed)
- $[a,b)$ or $(a,b]$ (half open)
- $\mathbb{R}^{+} = (0,\infty)$
- $\mathbb{R}^{+}_{0}=[0,\infty)$
- $\mathbb{R}^{-}=(-\infty,0)$
- $\mathbb{R}^{-}=(-\infty,0]$
- $\mathbb{R}=(-\infty,\infty)$

### Bounds
- $\text{max}(X)=x_{0}\in X$ s.t. $\forall x \in X : x \le x_{0}$ (maximum)
- $\text{min}(X)=x_{0}\in X$ s.t. $\forall x \in X : x \ge x_{0}$ (minimum)
- In cases where there is no explicit maximum and/or minimum, these concepts are substituted by the **supremum** and **infimum**, which can be understood as "infinitely good" bounds. 
- $\text{sup}(X)$ is the lowest upper bound (LUB)
- $\text{inf(X)}$ is the greatest lower bound (GLB)

### Properties of Bounds
- Maxima and minima are unique (if they exist)
- Every subset with a lower (upper) bound has a unique infimum (maximum) 

### Real Numbers ($\mathbb{R}$) 
- $\mathbb{R}$ can be rigorously axiomatically defined 
	*see page 12 in the script*
- $\mathbb{R}$ is ordered and consistent

### Properties of Absolute Values
- $|x+y|\le |x|+|y|$
- $|x+y|\ge||x|-|y||$

### Young's Inequality
For every $\varepsilon>0$ and all $x,y \in \mathbb{R}$ it holds that 

$$
2|xy|\le \varepsilon x^{2} + \frac{1}{\varepsilon}y^{2}
$$

This provides an upper bound for a product, its applications will be seen later. 