#HS2025 #DM 

## Pigeonhole Principle

1. Von 100 Personen haben mindestens 9 im gleichen Monat ihren Geburtstag.

Wir verwenden Theorem 2.10 mit $n = 100$, $k = 12$. Also haben nach Theorem 2.10 mindestens $\lceil\frac{n}{k}\rceil=g$ Personen im gleichen Monat Geburtstag.

2. In einem Laden gibt es 50 Kisten jede Kiste enthält höchstens 23 Äpfel. Zeige, es gibt mindestens 3 Kisten gibt, die genau gleich viele Äpfel enthalten. 

$M=\{ k_{1},\dots,k_{50} \}, M_{i}=\{ k_{j}\mid k_{j}\text{ enthält }i \text{ Äpfel } \}$ für $0\le i\le 23$. Wir verwenden Theorem 2.10 mit $n=50$, $k=24$. Also enthalten nach Theorem 2.10 mindestens $\left\lceil  \frac{n}{k}  \right\rceil=3$ Kisten gleich viele Äpfel. 

## Welche Definitionen beschreiben die gleiche Menge?

$$
\begin{align}
A= & \{ x\in \mathbb{Z}\mid x^{2}-8x+15=0 \} \\
B= & P(\varnothing) \\
C= & \{ x\in \mathbb{Z}\mid(x\text{ ungerade})\land(2\le x < 7) \} \\
D= & \{ x\in \mathbb{Z}\mid x > -1 \} \\
E= & \{ n\ge 1\mid n\text{ teilt }12\}\cap \{ n\ge 1 |n\text{ teilt }21\} \\
F= & \{ \varnothing \} \\
G= & \{ \varnothing,\{ \varnothing \} \} \\
H= & \{ n\ge 1 \mid n\text{ teilt }3 \} \\
I = & \mathbb{N}
\end{align}
$$
Wir haben $B=F, A=C, D=I$

## Subset Proof

$A\subseteq B \overset{\text{ def}}\iff \forall x(x\in A\to x\in B)$

Behauptung: $A\subseteq B$

Beweis: sei $a\in A$ beliebig $a\in A\implies\dots \implies a\in B$

1. Behauptung: $A\subseteq B$ und $B\subseteq C\implies A\subseteq C$

Beweis: Seien $A,B,C$ beliebige Mengen und nehme an $A\subseteq B$ und $B\subseteq C$. Sei $a\in A$ beliebig.

$$
\begin{align}
a\in A & \dot\implies a\in B  & (A\subseteq B) \\
 & \dot\implies a\in C & (B\subseteq C) \\
\end{align}
$$
Da alle Elemente von $A$ auch Elemente von $C$ sind, haben wir $A\subseteq C$.

2. Behauptung: $A\subseteq B$ und $C\subseteq D$ und $B\cap D\not=\varnothing\implies A\cap C\not=\varnothing$

Gegenbeispiel: $A=\{ 1 \}, B=\{ 1,2 \},C=\{ 3 \}, D=\{ 2,3 \}$ Dann $A\subseteq B$ und $C\subseteq D$ und $B\cap D=\{ 2 \}\not=\varnothing$ aber $A\cap C=\varnothing$.

## Set Equality

$A=B \overset{\text{ def}}\iff \forall x(x\in A\leftrightarrow x\in B)$

### Subset Proofs
1. $A\subseteq B$
2. $B\subseteq A$
3. $1 \land 2 \implies A=B$

### Set Algebra
1. Umformungen mit Set Algebra Gesetzen
2. Gleiche Definition erreichen

### Beispiele

1. Zeige $B\cup C \setminus A=(B\setminus A)\cup (C \setminus A)$

Seien $A,B,C$ beliebige Mengen. Sei $x$ beliebig. 

$$
\begin{align}
x\in (B\cup C)\setminus A  & \dot\iff x \in (B\cup C)\land \neg(x\in A) & (\text{Def. } \setminus) \\
 & \dot\iff (x\in B \lor x \in C )\land \neg(x \in A) & (\text{Def. }\cup) \\
 & \dot\iff (x\in B \land \neg(x\in A))\lor (x\in C\land\neg(x\in A)) & (\text{dist.}) \\
 & \dot\iff x \in B\setminus A \lor x\in C\setminus A & (\text{Def. }\setminus) \\
 & \dot\iff x\in((B\setminus A)\cup (C\setminus A))  & (\text{Def. }\cup)
\end{align}
$$

Somit haben wir also $(B\cup C)\setminus A=(B\setminus A)\cup(C\setminus A)$

2. $(B\cup C)\setminus A=(B\setminus A)\cup (C\setminus A)$

Seien $A,B,C$ beliebige Mengen, wir zeigen $(B\cup A)\setminus A \subseteq(B\setminus A)\cup (C\setminus A)$ und vice-versa. 

($\subseteq$) Sei $x\in(B\cup C)\setminus A$ beliebig

$$
\begin{align}
x\in(B\cup C)\setminus A  & \dot\implies x\in B\cup C & (\text{Def. }\setminus) (1)\\
x\in (B\cup C)\setminus A & \dot\implies x\not\in A  & (\text{Def. }\setminus)(2)
\end{align}
$$

Case distinction
1. $x\in B(3)$    $(2)(3)\implies x\in B\setminus A \ (\text{Def. }\setminus)\implies x\in (B\setminus A)\cup (C\setminus A)\ (\text{Def. }\cup)$
2. $x\not\in B (4)$    $(1)(4)\implies x\in C \ (5)(\text{Def. }\cup)$   $(2)(5)\implies x\in C\setminus A\implies x\in (B\setminus A)\cup(C\setminus A)$

