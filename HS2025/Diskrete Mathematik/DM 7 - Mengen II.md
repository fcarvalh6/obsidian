#HS2025 #DM 

## Mengen

**Lemma:** $A \subseteq B$ und $B \subseteq C \implies A \subseteq C$

**Bemerkung:** $\{ a,a \}=\{ a \}$ und $\{ a,b \}=\{ b,a \}$

$(a,b)\overset{\text{def}}=\{ a,\{ a,b \} \}$

**Lemma:** $(a,b)=(c,d)\iff(a=c)\land(b=d$
- Wir werden auch Liste der Form $a_{1},\dots,a_{k}$ benutzen.

**Definition:** $A\cup B \overset{\text{def}}=\{ x|x\in A\lor x\in B \}$ und $A\cap B \overset{\text{def}}=\{ x|x\in A\land x\in B \}$
- Existenz muss durch Axiome gesichert werden.

**Definition:**
- $\cup A \overset{\text{def}}= \{ x|x\in A\text{ für (mind.) ein }A\in A \}$
- $\cap A\overset{\text{def}}=\{ x|x\in A\text{ für alle }A\in A \}$

**Theorem 3.4**
- $A\cup A=A$ und $A\cap A=A$
- $A\cap B=B\cap A$ und $A\cup B = B \cup A$
- $A\cap(B\cap C)=(A\cap B)\cap C$ und $A\cup(B\cup C)=(A\cup B)\cup C$
- $A\cap(A\cup B)=A$ und $A\cup(A\cap B)=A$
- $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$ und $A\cup(B\cap C)=(A\cup B)\cap(A\cup C)$
- $A\subseteq B\iff A\cap B=A\iff A\cup B=B$

Ein Beweis: 

$$
\begin{align}
A\cap(B\cup C) = & \{ x\mid x\in A \land x\in B\cup C \} \\
= & \{ x\mid x\in A \land x \in \{ x\mid x\in B \lor x \in C \} \} \\
= & \{ x\mid x\in A \land (x\in B \lor x \in C) \} \\
= & \{ x\mid (x \in A \land x\in B)\lor (x\in A\land x \in C) \} \\
= & \{ x\mid x \in (A\cap B)\lor x\in (A\cap C) \} \\
= & (A\cap B)\cup(A\cap C)
\end{align}
$$

**Definition:** $B \setminus A \overset{\text{def}}=\{ x\in B \mid x \not\in A\}$

**Natürliche Zahlen** ($\mathbb{N}$)

$$
\begin{align}
 0 \overset{\text{def}}= & \varnothing \\
1\overset{\text{def}}= & \{ \varnothing \} \\
2\overset{\text{def}}= & \{ \varnothing, \{ \varnothing \} \} \\
3\overset{\text{def}}= & \{ \varnothing,\{ \varnothing,\{ \varnothing \} \} \} \\
\vdots &  \\
S(n )\overset{\text{def}}= & n\cup \{ n \}
\end{align}
$$

Addition:

$$
\begin{align}
m+0\overset{\text{def}}= & m \\
m+S(n) \overset{\text{def}}= & S(m+n) \\
\end{align}
$$

$$
\mathbb{N}=\{ 0, 1, 2, \dots \}\qquad \text{muss axiomatisch begründet werden}
$$

**Definition:** Potenzmenge $P(A)= \{ S\mid S \subseteq A \}$

$$
\begin{align}
P(\varnothing)  & = \{ \varnothing \} \\
P(\{ \varnothing \}) & = \{ \varnothing,\{ \varnothing \} \} \\
P(\{ 1, 5, 7 \}) & =\{ \varnothing,\{ 1\},\{ 5 \},\{ 7 \},\{ 1,5 \},\{ 1,7 \},\{ 5,7 \},\{ 1,5,7 \} \}
\end{align}
$$

## Kartesische Produkte

**Definition:** $A\times B=\{ (a,b)\mid a\in A \land b \in B \}$

$$
\bigtimes_{i=1}^k A_i = \{ (a_{1},a_{2},\dots,a_{k})\mid a_{i}\in A_{i} \text{ für } i=1, \dots,k \}
$$

Beispiel:

$$
\begin{align}
\varnothing \times A  & = A \times \varnothing = \varnothing \\
\{ 1, 2 \}\times \{ 3, 4 \} & = \{ (1,3),(1,4),(2,3),(2,4) \}
\end{align}
$$

