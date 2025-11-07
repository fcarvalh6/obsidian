#HS2025 #DM 

Monoid mit einseitigen Inversen:

$\langle \mathbb{N}^{\mathbb{N}} ; \circ , \text{id}_{\mathbb{N}}\rangle, \ f:n\mapsto n+1$ (hat LI, aber kein RI) 

**Def.:** Direktes Produkt $\langle G_{1}\times G_{2};* \rangle$ von Gruppen $\langle G_{1};*_{1} \rangle$ und $\langle G_{2};*_{2} \rangle$ gegeben durch $(a_{1},a_{2})*(b_{1},b_{2}) \stackrel{\text{ def.}}=(a_{1}*_{1}b_{1},a_{2}*_{2}b_{2}).$ Schreibweise: $\langle G_{1};*_{1} \rangle\times \langle G_{2} ; *_{2}\rangle$ 

Mögliche Gruppen (endlich, $|S|=n$)

$n=1$

| $*$ | e   |
| --- | --- |
| e   | e   |
$\langle \mathbb{Z}_{1};\oplus_{1} \rangle$

$n=2$

| $*$ | e   | a   |
| --- | --- | --- |
| e   | e   | a   |
| a   | a   | e   |
$\langle \mathbb{Z}_{2};\oplus_{2} \rangle$

$n=3$

| $*$ | e   | a   | b   |
| --- | --- | --- | --- |
| e   | e   | a   | b   |
| a   | a   | b   | e   |
| b   | b   | e   | a   |
$\langle \mathbb{Z}_{3};\oplus_{3} \rangle$

$n=4$


| $*$ | e   | a   | b   | c   |
| --- | --- | --- | --- | --- |
| e   | e   | a   | b   | c   |
| a   | a   | e   | c   | b   |
| b   | b   | c   | e   | a   |
| c   | c   | b   | a   | e   |
$\langle \mathbb{Z}_{2}\times \mathbb{Z}_{2};\oplus_{2} \rangle$

auch möglich $\langle \mathbb{Z}_{4};\oplus_{4} \rangle$ 

$n=5$ $\langle \mathbb{Z}_{5};\oplus_{5} \rangle$ einzige Gruppe (bis auf Elemente), Behauptung.

Schreibweise: 
- $\mathbb{Z}_{m}$ (oder $\mathbb{Z}_{m}^{+}$) für $\langle \mathbb{Z}_{m};\oplus_{m},\ominus_{m},0 \rangle$. 
- $\mathbb{Z}_{m}^{*}$ für $\langle \{ x\in \mathbb{Z}_{m}\mid \text{gcd}(x,m)=1 \},\odot_{m},\text{mod. Inv.},1 \rangle$

Beispiel: $\mathbb{Z}_{6}^{*}=\langle \{ 1,5 \},\odot_{6},\text{mod. Inv.},1 \rangle$ 

$n=6$ $\mathbb{Z}_{6}$, aber auch $S_{3}=\langle \{ f:\mathbb{Z}_{3}\to\mathbb{Z}_{3}\text{ bijektiv},\circ,\text{id}_{\mathbb{Z}_{3}} \} \rangle$ (nicht kommutativ)

**Vermutung:** $n$ prim $\implies \mathbb{Z}_{m}$ einzige Gruppe (bis auf Umbenennung) 

**Def.:** für Gruppen $\langle G_{1};*_{1} \rangle,\langle G_{2};*_{2} \rangle$ ist eine Funktion $\psi:G_{1}\to G_{2}$ ein Gruppenhomomorphismus, falls $\forall a_{1}\in G_{1}\ \forall b_{1}\in G_{1} \quad \psi(a_{1}*_{1}b_{1})=\psi(a_{1})*_{2}\psi(b_{1}).$ Wenn $\psi$ bijektiv ist, dann ist $\psi$ Isomorphismus (und $G_{1},G_{2}$ isomorph, $G_{1}\simeq G_{2}$).

Beispiel: $\langle \mathbb{Z}_{6};\oplus_{6} \rangle \simeq \langle \mathbb{Z}_{3};\oplus_{3} \rangle\times \langle \mathbb{Z}_{2};\oplus_{2} \rangle$ 

$\psi(1)=(1,1)$
$\psi(0)=(0,0)$ 

aber $\langle \mathbb{Z}_{4};\oplus_{4} \rangle \not\simeq \langle \mathbb{Z}_{2};\oplus_{2} \rangle\times \langle \mathbb{Z}_{2};\oplus_{2} \rangle$

$\psi(1)=(a,b)$
$\psi(1\oplus_{4}1)=(a\oplus_{2}a,b\oplus_{2}b)$ funktioniert nicht, LS $\not=0$ und RS $=0$

**Lemma 5.5:** Sei $\psi$ Homomorphismus von $\langle G_{1};*_{1} \rangle$ nach $\langle G_{2};*_{2} \rangle$. Dann gilt: $\psi(e_{1})=e_{2}$ und $\psi(\hat{a_{1}})=\widehat{\psi(a_{1})}$, für alle $a_{1}\in G_{1}$ 

Weiteres Beispiel: $\mathbb{Z}_{6}^{*}\simeq \mathbb{Z}_{2}$, ohne Beweis $\mathbb{Z}_{15}^{*}\simeq \mathbb{Z}_{2}\times \mathbb{Z}_{4}$

$f:\mathbb{Z}_{2} \to S_{3}$

**Def.:** Für eine Gruppe $\langle G;*,\hat{},e \rangle$ ist $H\subseteq G$ Untergruppe, wenn $\langle H,*,\hat{},e \rangle$ Gruppe.

Beispiel: $\mathbb{Z}_{8}$ hat $UG\quad \{ 0 \},\{ 0,4 \},\{ 0,2,4,6,8 \},\mathbb{Z}_{8}$ 