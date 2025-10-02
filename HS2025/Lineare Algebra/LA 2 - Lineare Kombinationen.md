#HS2025 #LA 

## Punktlose Notation
- Folge von Vektoren: $v_{1},v_{2},\dots,v_{n} = (v_{j})_{j=1}^n$
- Linearkombinationen: $\lambda_{1}v_{1} +\lambda_{2}v_{2} + \dots \lambda_{n}v_{n} = \sum _{j=1}^n\lambda _{j}v_{j}$
- Menge von Vektoren: $\{v_{1},v_{2},\dots,v_{n}\} = \{v_{j}: j\in[n]\}$
- Vektoren: 
$$
\mathbf{v} = \begin{pmatrix}
v_{1} \\
v_{2} \\
\vdots \\
v_{n}
\end{pmatrix}
= (v_{i})_{i=1}^{m} 
$$
## Skalarprodukte, Längen, Winkel

### Skalarprodukt

Seien $$
\mathbf{v}= \begin{pmatrix}
v_{1} \\
v_{2} \\
\vdots \\
v_{n}
\end{pmatrix}, \mathbf{w}= \begin{pmatrix}
w_{1} \\
w_{2} \\
\vdots \\
w_{n}
\end{pmatrix} \in \mathbb{R}^{m} 
$$
Das Skalarprodukt von $\mathbf{v}$ und $\mathbf{w}$ ist die Zahl $$
\mathbf{v} \cdot \mathbf{w} := \sum_{i=1}^{m}v_{i}w_{i}
$$
Beobachtung: Seien $\mathbf{u,v,w} \in \mathbb{R}^{m}, \lambda\in\mathbb{R}$.
$(i) \quad \mathbf{v}\cdot \mathbf{w} = \mathbf{w}\cdot \mathbf{v}$
$(ii) \quad (\lambda \mathbf{v})\cdot \mathbf{w} = \lambda(\mathbf{v}\cdot \mathbf{w})=\mathbf{v}\cdot(\lambda \mathbf{w})$
$(iii)$ %1
$(iv) \quad \mathbf{v}\cdot \mathbf{v}\geq 0$ mit Gleichheit genau dann, wenn $\mathbf{v}=0$


### Euklidische Norm: definiert die Länge eines Vektors

Sei $\mathbf{v}= \mathbb{R}^{m}$. Die euklidische Norm von $\mathbf{v}$ ist die Zahl $$
||\mathbf{v}||=\sqrt{ \sum_{i=1}^{m}v_{i}^{2} }
$$
Einheitsvektor: $||\mathbf{u}|| = 1$
$$
\frac{1}{||\mathbf{v}||}\mathbf{v}\quad\text{ist ein Einheitsvektor}
$$

### Cauchy-Schwarz-Ungleichung (& Skript)

Für je zwei Vektoren $\mathbf{v},\mathbf{w}\in \mathbb{R}^m$ gilt: $|\mathbf{v}\cdot \mathbf{w}| \leq ||\mathbf{v}||\cdot||\mathbf{w}||$

Gleichheit gilt genau dann, wenn einer der Vektoren ein skalare Vielfaches des anderen ist. 

### Winkel

Seien $\mathbf{v},\mathbf{w} \in \mathbb{R}^m$, beide ungleich 0. Der Winkel zwischen ihnen ist das eindeutige $\alpha$ zwischen 0 und 180 Grad, so dass
$$
\cos(\alpha) = \frac{{\mathbf{v}\cdot \mathbf{w}}}{||\mathbf{v}||\cdot||\mathbf{w}||}\in [-1,1]
$$
Orthogonale Vektoren: $\mathbf{v},\mathbf{w}\in \mathbb{R}^m$ heissen orthogonal wenn $\mathbf{v}\cdot \mathbf{w}=0$

### Dreiecksungleichung

Seien $\mathbf{v},\mathbf{w}\in \mathbb{R}^m$. Dann gilt $||\mathbf{v}+\mathbf{w}|| \leq ||\mathbf{v}||+||\mathbf{w}||$

## Hyperebenen

Sei $d\in \mathbb{R}^m, d \neq 0$. Die Menge $H_{d} = \{\mathbf{v}\in \mathbb{R}^m:\mathbf{v}\cdot \mathbf{d}=0\}$
