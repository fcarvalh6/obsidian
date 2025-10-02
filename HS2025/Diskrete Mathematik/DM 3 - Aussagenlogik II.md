#HS2025 #DM 

**Beobachtung:** $F \to G\;\text{allgemeingültig}\;\iff F\vDash G$

**Beispiel:**

| A   | B   | $A \to B$ | $A\land(A\to B)$ | $(A\land(A\to B))\to B$ |
| --- | --- | --------- | ---------------- | ----------------------- |
| 0   | 0   | 1         | 0                | 1                       |
| 0   | 1   | 1         | 0                | 1                       |
| 1   | 0   | 0         | 0                | 1                       |
| 1   | 1   | 1         | 1                | 1                       |
daraus folgt: $A\land(A\to B) \vDash B$

## Modus Ponens

Vorgehen (für eine Aussage S)
1. Finde geeignete Aussage R
2. Beweise R
3. Beweise R $\implies$ S

Falsche/Schlechte Beweisstrategie
- Theorem: $1 < 0$
- Beweis: 
$$
1 < 0 \implies 2<1 \qquad\text{ +1 beide Seiten}
$$
$$
\implies 2 > 1 \qquad \cdot\text{1, negativ}
$$
Aussage ist wahr.

**Lemma 2.1**
1. $A\land A \equiv A$ und $A \lor A \equiv A$
2. $A\land B \equiv B\land A$ und $A\lor B \equiv B \lor A$
3. $A\land (B\land C)\equiv(A\land B)\land C$ und $A\lor (B\lor C)\equiv(A\lor B)\lor C$
4. $A\land(A\lor B)\equiv A$ und $A\lor(A\land B)\equiv A$
5. $A\land(B\lor C)\equiv(A\land B)\lor(A\land C)$
6. $A\lor(B\land C)\equiv(A\lor B)\land(A\lor C)$
7. $\neg\neg A\equiv A$
8. $\neg(A\land B) \equiv \neg A \lor \neg B$ und $\neg(A\lor B) \equiv \neg A \land \neg B$

$$
A\land(A\to B)\equiv A\land(\neg A\lor B) \qquad \text{Begründung: }(A\to B \equiv \neg A \lor B)
$$
$$
\equiv (A\land\neg A)\lor(A\land B) \qquad \text{(Lemma 2.1.5)}
$$
$$
\equiv \bot \lor (A\land B) \qquad (A\land\neg A\equiv\bot)
$$
$$
\equiv (A\land B)\lor \bot \qquad \text{(Lemma 2.1.2)}
$$
$$
\equiv A \land B \qquad (F \lor \bot \equiv F)
$$
$$
\vDash B \qquad (A\land B \vDash B)
$$
Obs: Formeln können als Bäume dargestellt werden

## Prädikatenlogik

Motivation: Aussagenlogik ist begrenzt in ihre Aussagekraft

Bausteine der Prädikatenlogik:
- Universum U                ( $\mathbb{N},\; \mathbb{R}$, $\{0,1\}$)
- Konstanten aus U        ($0,1,\pi$)
- Prädikate P, Q, ...          (prime(x), less(x, y)) (Ausgabe immer 0 oder 1)
- Funktionen f, g, ...        (square(x), add(x, y)) (Ausgabe immer Element aus U)
- Operatoren                  ($\neg, \land, \lor,\to$)
- Quantoren                   ($\forall x, \exists x$)

Allgemein
- $\exists x \ (F\land G)$ %

Spezielle Interpretation:
- $U = \mathbb{N}$ 
- $\forall x \ (0\leq x)$ *wahr*
- $\exists x \ (x\leq 2)\land \exists x \ (3\leq x)$ *wahr*

