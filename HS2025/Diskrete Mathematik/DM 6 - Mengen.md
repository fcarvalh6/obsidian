#HS2025 #DM 

## Naive Verständnis

Menge von Objekten, $\mathbb{N}=\{ 0,1,2,\dots \}, 1\in \mathbb{N},\subseteq,=,\varnothing\text{ leere Menge}$

$A=\{ \varnothing,\{ \varnothing \} \}, A=\{ 0,1,2,\dots \}\cup\{\sqrt{ 2 }\}$

$A=\{ \text{alle Mengen mit} \ge 3 \text{ Elementen} \}= \{ M \text{ Menge} \;|\; |M| \ge 3 \}\implies A\in A$

$A=\{ M\text{ Menge} | M\not\in M \}\qquad A\in A\implies A\not\in A\implies A\in A$

### Lösung: Existenz und Konstruktion von Mengen reformulieren

Neuanfang mit Universum von Objekten ("Mengen") und Prädikat $E(x,y)$ (Schreibweise $x\in y$ für $E(x,y)$)

Definition: gleiche enthaltene Elemente $(\forall x((x\in A))\leftrightarrow(y\in B))\implies$gleiche Menge $(A=B)$

**Axiom:** Menge $A$, die nur aus 1 Element $x$ besteht, existiert. $\forall y((x\in A)\leftrightarrow(x=y))$
- Schreibweise: $\{ x \}$, analog für $\{ x_{1},\dots,x_{n} \}$

**Lemma:** $\{ a \}=\{ b \}\implies a=b$
- Beweis (indirekt): $\neg(a=b)\implies \neg(\{ a \}=\{ b \})$

Schreibe $A \subseteq B$, falls $\forall x ((x \in A)\to(x\in B))$ wahr

**Lemma:** $A=B\iff(A\subseteq B)\land(B\subseteq A)$ wahr
- Beweis: 

$$
\begin{align}
(A\subseteq B)\land(B\subseteq A)\dot\iff & \forall (x((x\in A)\to(x\in B)))\land (\forall x((x\in B)\to(x\in A)))\\
\dot\iff& \forall x(((x\in A)\to(x\in B))\land((x\in B)\to(x\in A))) \\
\dot\iff & \forall x((x\in A)\leftrightarrow(x\in B))\\
\dot\iff & A = B & (\text{Def. =})
\end{align}
$$

Leere Menge $\varnothing$ ist Menge mit $\forall x (x\not\in\varnothing)$ wahr
- $\varnothing$ eindeutig bestimmt $\varnothing,\varnothing'$ leer $\implies \varnothing=\varnothing'$ nach Def. "="

**Lemma:** $\forall A(\varnothing\subseteq A)$

Beispiel:

$$
\begin{align}
A = & \{ \{ \varnothing \} \} \\
B= & \{ \{ \varnothing \}\{ \varnothing,\varnothing \} \} \\
C= & \{ \varnothing,\{ \varnothing \} \} \\
D= & \{ \varnothing,\{ \varnothing,\{ \varnothing \} \} \}
\end{align}
$$