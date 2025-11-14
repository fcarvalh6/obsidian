#HS2025 #LA 

**Geometrische Interpretation:** wir schreiben $b=p+e$ mit $p \in S,e \in S^{\bot}$. $\operatorname{proj}_{s}(b)=p$  

Wir haben gezeigt, wenn $S=\{ a\cdot\lambda\mid\lambda \in R \}$ und $a \in \mathbb{R}^{m}\setminus\{ 0 \}$, dann $\operatorname{proj}_{s}(b)=\frac{1}{\lvert \lvert a \rvert \rvert^{2}}a\cdot a^{\top}b$ 
Betrachte $S \subseteq \mathbb{R}^{m}$. Sei $a_{1},\dots,a_{n}\in \mathbb{R}^{n}$, sei $S=\left\{  \sum_{i=1}^{n}a_{i}\lambda_{i}\mid \lambda_{1},\dots,\lambda_{n}\in \mathbb{R}  \right\} = \{ A\lambda \mid \lambda\in \mathbb{R}^{n} \}$.

**Lemma 5.2.3:** Die Projektion von $b \in \mathbb{R}^{m}$ auf $S=C(A)$ ist ein Vektor $A\cdot \hat{\mathbf{x}},\hat{\mathbf{x}} \in \mathbb{R}^{n}$ mit $A^{\top}A\cdot \hat{\mathbf{x}}=A^{\top}\mathbf{b}$ 

Beweis: $b=p+e$ mit $p \in S,e \in S^{\bot}$, d.h. $p^{\top}e=e^{\top}p=0$. Vermutung: $p=A\cdot \hat{\mathbf{x}}$.

Sei $p' \in S \implies p-p'\in S\implies e^{\top}(p-p')=0\iff(b-p)^{\top}(p-p')=0$

$\lvert \lvert p'-b \rvert \rvert^{2}=\lvert \lvert (p'-p)+(p-b) \rvert \rvert^{2}=\lvert \lvert p'-p \rvert \rvert^{2}+\lvert \lvert p-b \rvert \rvert^{2}>\lvert \lvert p-b \rvert \rvert^{2}$ 

Wir haben gezeigt: $\operatorname{proj}_{s}(b)=p$ 

$e=b-p \in S^{\bot}\implies b-\operatorname{proj}_{s}(b)$ orthogonal zu $a_{i}\forall i=1\dots n\iff a_{i}^{\top}(b-\operatorname{proj}_{s}(b))=0$

$A^{\top}(b-\operatorname{proj}_{s}(b))=0$ $(\operatorname{proj}_{s}(b))=A \hat{\mathbf{x}}$

d.h. $A^{\top}\mathbf{b}-A^{\top}A \hat{\mathbf{x}}=0$

**Lemma 5.2.4:** Sei $A \in \mathbb{R}^{m\times n}$. Dann gilt $A^{\top}A$ ist invertierbar $\iff$ spalten von $A$ sind linear unabhängig. 

Beweis: 

$N(A^{\top}A)=N(A),A^{\top}A$ invertierbar $\iff N(A^{\top}A)=\{ 0 \}\iff N(A)=\{ 0 \}$, d.h. Spalten von $A$ sind linear unabhängig. 

**Theorem 5.2.5:** Sei $A \in \mathbb{R}^{m\times n}$, Spalten von $A$ sind linear unabhängig und $S=C(A).$ Dann gilt für alle $\mathbf{b}\in\mathbb{R}^{m}$.
$$
\operatorname{proj}_{s}(\mathbf{b})=P\cdot \mathbf{b}
$$
wobei $P$ die folgende Matrix (Projektionsmatrix) ist.

$$P=A(A^{\top}A)^{-1}A^{\top}$$
Beweis: $\operatorname{proj}_{s}(b)=A\cdot  \hat{\mathbf{x}}$, mit $\hat{\mathbf{x}}\in \mathbb{R}^{n}$ und $\hat{\mathbf{x}}=(A^{\top}A)^{-1}A^{\top}\mathbf{b}$

