#HS2025 #DM 


## Representations of Relations

**Graph:** $1\to 2 \to 1 \to 3 \to 2$

**Menge:** $\rho=\{ (1,2),(2,1),(1,3),(3,2) \}$

**Matrix:** $M_{a,b}^\rho=1 \iff a \rho b$

$$
\begin{bmatrix}
0 & 1 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix}
$$

### Inverse 

**Graph:** umgedrehte Kanten

**Menge:** $\hat{\rho}=\{ (a,b)\mid (b,a)\in \rho \}$

**Matrix:** $M^T$

### Komposition ($\rho^{2}$)

**Graph:** $2\to 3 \to 1 \to 2$ (2 Kanten folgen)

**Menge:** $\rho\circ\rho = \{ (a,c)\mid \exists b((a,b)\in \rho \land (b,c)\in \rho) \}$

**Matrix:** $M\odot M$


|     | a   | b   | c   | d   |
| --- | --- | --- | --- | --- |
| a   | 0   | 1   | 0   | 1   |
| b   | 1   | 0   | 1   | 0   |
| c   | 0   | 1   | 0   | 1   |
| d   | 1   | 0   | 1   | 0   |
- reflexiv: nein
- irreflexiv: ja
- symmetrisch: ja
- antisymmetrisch: nein
- transitiv: nein

## Beweise

### Beispiel 1

$\rho \subseteq \mathbb{R}\times \mathbb{R}, \rho=\{ (a,b)\mid(a-b)\text{ ist eine ganze Zahl} \}$. Zeige, dass $\rho$ eine Äquivalenzrelation ist. 

Reflexiv: sei $a\in \mathbb{R}$ beliebig. $a-a=0 \implies(a-a)\in \mathbb{Z}<\implies(a,a)\in \rho$

Symmetrie: seien $a,b\in \mathbb{R}$ beliebig. Annahme: $(a,b)\in \rho$
$(a,b)\in \rho\implies(a-b)\in Z\implies-(a-b)\in \mathbb{Z}\implies (b-a)\in \mathbb{Z}\implies(b,a)\in \rho$

Transitiv: seien $a,b,c\in \mathbb{R}$ mit $(a,b)\in \rho,(b,c)\in \rho$ beliebig
$(a,b)\in \rho \dot\implies(a-b)\in \mathbb{Z} \quad (1)$ und $(b,c)\in \rho \dot\implies (b-c)\in \mathbb{Z} \quad (2)$

$(1),(2)\implies\left( (a-b)+(b-c)\right)\in \mathbb{Z}\implies (a-c)\in \mathbb{Z}\implies(a,c)\in \rho$

### Beispiel 2

Seien $\rho,\sigma$ Relationen auf $A$. Widerlege: Falls $\rho$ und $\sigma$ transitiv sind, ist auch $\rho\cup\sigma$ transitiv.

$A=\{ 1,2,3 \},\rho=\{ (1,2) \},\sigma=\{ (2,3) \}.$ Dann ist $\rho\cup \sigma=\{ (1,2),(2,3) \}$, also ist $\rho\cup\sigma$ nicht transitiv $((1,3)\not\in \rho\cup\sigma)$, aber $\rho$ und $\sigma$ sind transitiv. 

### Beispiel 3

Seien $\rho,\sigma$ Äquivalenzrelationen auf eine Menge $A$ mit $\rho\circ\sigma=\sigma\circ\rho$. Zeige, dass $\rho\circ\sigma$ eine Äquivalenzrelation ist. (Def. $\rho\circ\sigma=\{ (a,c)\mid\exists b((a,b)\in \rho \land(b,c)\in \sigma) \}$)

Reflexiv: sei $a\in A$ beliebig. $a\in A\implies(a,a)\in \rho \ (1)$ und $a\in A\implies(a,a)\in\sigma \ (2)$
$(1)(2)\implies(a,a)\in \rho\circ\sigma$

Symmetrisch: seien $a,b\in A$ beliebig. $(a,b)\in \rho\circ \sigma\implies(a,x)\in\rho$ und $(x,b)\in \sigma$ für ein $x\in A$
$\implies(x,a)\in \rho$ und $(b,x)\in \sigma$ für ein $x\in A$ 
$\implies (b,a)\in \sigma\circ \rho \implies(b,a)\in \rho\circ\sigma$ 

Transitiv: seien $a,b,c\in A$ mit $(a,b)\in \rho\circ\sigma$ und $(b,c)\in \rho\circ\sigma$ beliebig. 
$(a,b)\in \rho\circ\sigma$ und $(b,c)\in \rho\circ\sigma$
$\implies(a,x)\in \rho$ und $(x,b)\in\sigma$ und $(b,y)\in \rho$ und $(y,c)\in \sigma$ für $x,y\in A$
$\implies(a,x)\in \rho$ und $(x,y)\in\sigma\circ\rho$ und $(y,c)\in\sigma$ für $x,y\in A$ 
$\implies (a,x)\in \rho$ und $(x,y)\in \rho\circ\sigma$ und $(y,c)\in\sigma$ für $x,y\in A$
$\implies(a,x)\in\rho$ und $(x,z)\in \rho$ und $(z,y)\in\sigma$ und $(y,c)\in\sigma$ für $x,y,z\in A$
$\implies(a,z)\in \rho$ und $(z,c)\in\sigma$ ... 