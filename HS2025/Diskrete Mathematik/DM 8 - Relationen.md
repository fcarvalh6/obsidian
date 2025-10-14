#HS2025 #DM 

**Def.:** Relation $\rho$ von $A$ zu $B$ ist Untermenge von $A\times B$ 

**Inverse Relation** (oder Umkehrrelation) $\hat{\rho} \overset{\text{def}}=\{ (b,a)\mid(a,b)\in \rho \}$

**Schreibweise:** $a \ \rho \ b$ statt $(a,b)\in\rho$

**Komposition von Relationen:** $\rho \circ \sigma\overset{\text{def}}= \{ (a,b)\mid \exists b((a,b)\in \rho \land (b,c)\in \sigma) \}$

**Lemma 3.7:** $\rho\circ(\sigma \circ \phi)=(\rho\circ \sigma)\circ \phi$

**Lemma 3.8:** $\hat{\rho\circ \sigma}=\hat{\sigma} \circ \hat{\rho}$

Beweis:

$$
\begin{align}
a \ \hat{\rho \sigma} \ c  &\dot\iff c \ \rho \sigma \ a \\
 & \dot\iff \exists b(c \ \rho \ b \land b \ \sigma \ a) \\
 & \dot\iff \exists b (b \ \sigma \ a \land c \ \rho \ b) \\
 & \dot\iff \exists b (a \ \hat{\sigma}\ b \land b \ \hat{\rho} \ c) \\
 & \dot\iff  a \ \hat{\sigma}\hat{\rho} \ c
\end{align}
$$

Beispiel: 
- $\le$ Relation von $\mathbb{N}$ nach $\mathbb{N}$ (auf $\mathbb{N}$)
- $\hat{\le} = \; \ge$
- $\leq \; = \; < \cup \text{ id}_{\mathbb{N}}$
- $\le \circ \le \; = \; \le$
- $< \circ < \; = \{ (a,c)\mid a+2 \le c \} \not= \; <$
- $\le \cap \ge \; = \text{id}_{\mathbb{N}}$
- $\le \cap > \; =\varnothing$

Beispiel:
 $\equiv_{m}$ mit $x\equiv_{m} y \iff m\mid(x-y)$ Relation auf $\mathbb{Z}$

$\equiv_{m}$ hat interessante Eigenschaften: ($3\equiv_{7}10$ and $1 \not\equiv_{3}2$) 
- $\hat{\equiv}_{m} = \; \equiv_{m}$ 
- $\text{id}_{\mathbb{Z}}\subseteq \; \equiv_{m}$
- $x \equiv_{m}y$ und $y\equiv_{m}z \implies x\equiv_{m}z$

$H=$ Menge aller Menschen
- $\text{child}\subseteq H\times H$ mit $x \text{ child }y \iff x$ Kind von $y$ 
- $\hat{\text{child}}=\text{parent}$
- $\underbrace{\text{parent}\circ\text{parent}}_{\text{parent}^{2}}=\text{grandparent}$
- $(\text{ancestor}=\text{parent} \cup \text{parent}^{2}\cup \text{parent}^{3}\cup\dots)$
- $(\text{child}\circ\hat{\text{child}})\setminus \text{id}_{H}$ = $\text{(half-)sibling}$


| Name            | Formel                                                        | Mengen                                    | Beispiel               | Nicht-Bsp.  |
| --------------- | ------------------------------------------------------------- | ----------------------------------------- | ---------------------- | ----------- |
| reflexiv        | $\forall a(a \;\rho \;a)$                                     | $\text{id}\subseteq \rho$                 | $\text{id}, \le,\ge$   | $>$         |
| irreflexiv      | $\forall a\neg(a\;\rho\;a)$                                   | $\text{id}\cap\rho = \varnothing$         | $\not=, >,<$           | $\text{id}$ |
| symmetrisch     | $\forall a,b((a\;\rho\;b)\leftrightarrow(b\;\rho\;a))$        | $\hat{\rho}=\rho$                         | $\equiv_{m},\text{id}$ | $>$         |
| antisymmetrisch | $\forall a,b((a\;\rho\;b)\land(b\;\rho\;a))\to(a=b)$          | $\hat{\rho}\cap \rho \subseteq \text{id}$ | $\ge, >$               | $\not=$     |
| transitiv       | $\forall a,b,c((a\;\rho\;b)\land(b\;\rho\;c))\to(a\;\rho\;c)$ | $\rho^{2}\subseteq \rho$                  | $\equiv_{m},<$         | $\not=$     |

**Lemma 3.9:** $\rho \text{ transitiv}\iff\rho^{2}\subseteq \rho$

Beweis: 
- %