#HS2025 #DM 

**Hasse-Diagramme**

Bei gegebenem poset $(A;\preccurlyeq):b\in A\text{ überdeckt } a\in A \overset{\text{ def}}\iff a\prec b \land \neg \exists c(a\prec c\prec b)$

$(\{ 2,3,4,5,6,7,8,9 \};\mid)$ $(\{ 1,2,3,4,6,8,12,24 \};\mid)$ 

**Totalordnung:** $\forall a,b(a\preccurlyeq b\lor b \preccurlyeq a)$

**Wohlordnung:** $(A;\preccurlyeq )$ wohlgeordnet $\overset{\text{def}}\iff (A;\preccurlyeq)$ totalgeordnet und jede nicht leere Untermenge von A ein kleinstes Element hat.

## Direkte Produkt

$(A;\preccurlyeq)\times(B,\sqsubseteq)$, von posets $(A;\preccurlyeq)$ und $(B,\sqsubseteq)$ ist $(A\times B;\le)$ mit $(a_{1},b_{1}) \le(a_{2},b_{2})\overset{\text{ def}}\iff(a_{1}\preccurlyeq a_{2}) \land(b_{1}\sqsubseteq b_{2})$

**Theorem:** $(A\times B;\le)$ ist wieder ein poset.

Beweis: (Reflexivität) Für beliebige $a\in A$ und $b\in B$ gilt:
- $a\preccurlyeq a$ (Refl. $\preccurlyeq$)
- $b \sqsubseteq b$ (Refl. $\sqsubseteq$)
Also gilt $(a,b)\le(a,b)$ 

Für $(A;\preccurlyeq)$ und $(B;\sqsubseteq)$ ist auch $(A\times B;\le_{\text{lex}})$ mit $(a_{1},b_{1})\le_{\text{lex}}(a_{2},b_{2})\overset{\text{ def}}\iff a_{1}\prec a_{2}\lor (a_{1}=a_{2}\land b_{1} \sqsubseteq b_{2})$ ein poset.

## Funktionen

**Def.:** Relation $f\subseteq A\times B$ ist Funktion $A\to B$, falls $(\forall a \in A \ \exists b\in B \quad a \ f \ b)$ und $(\forall a\in A \ \forall b,b'\in B \quad a \ f \ b \land a \ f \ b' \to b=b')$

Schreibweise: $f(a)=b$ oder $f:a\mapsto b$ $f(A)=\{ f(a)\mid a \in A \}$

Ohne erste Bedingung: $f$ *partielle* Funktion

**Def.:** Funktion $f$ ist...
- injektiv, falls $\forall a,a'((f(a)=f(a'))\to(a=a'))$
- surjektiv, falls $\forall b\in B \ \exists a\in A (f(a)=b)$
- bijektiv, falls $f$ surjektiv und injektiv

Schreibweise: $g\circ f$ ist Funktion mit $(g\circ f)(a)=g(f(a))$ für Funktionen $f,g$ 

$A^B$ ist Menge aller Funktionen $f:A\to B$

**Lemma:** $f,g$ injektiv $\implies g\circ f$ injektiv

Beweis (indirekt): Sei $f,g$ injektiv, $a,a'$ beliebig

$$
\begin{align}
a\not= a'  & \dot\implies f(a)\not=f(a')  & (\text{Inj. }f) \\
 & \dot\implies g(f(a)) \not= g(f(a')) & (\text{Inj. }g) \\
 & \dot\implies(g\circ f)(a) \not = (g \circ f)(a')  & (\text{Def. }\circ)
\end{align}
$$

## Mächtigkeit von Mengen

**Def.:** 
- $A\preccurlyeq B$, falls injektive Funktion $f:A\to B$ existiert
- $A\sim B$, falls bijektive Funktion $f:A\to B$ existiert
- $|A|=n$, falls $A\sim n$ (Mengendefinition $\mathbb{N}$)
- $A$ abzählbar, falls $A\sim \mathbb{N}$ oder $A\sim n$ für ein $n\in \mathbb{N}$ ($A$ endlich)

