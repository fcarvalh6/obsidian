#FS2026 #AW 

We define a discrete probability space through a set of elementary events $\Omega=\{ \omega_{1}, \omega_{2},\dots \}$ . Every elementary event has a probability $\text{Pr}[\omega_{i}]$. We have $0\le \text{Pr}[\omega_{i}] \le 1$ and $\sum_{\omega \in\Omega}\text{Pr}[\omega]=1$.

An event $E$ is a subset of elementary events and $\text{Pr}[E]$ is the sum of probabilities of elementary events included in $E$.

**Laplace Spaces** are spaces where every elementary event has the same probability.

**Theorem:** for disjunct events:

$$
\text{Pr}\left[ \bigcup_{i=1}^{n}A_{i}\right]=\sum_{i=1}^{n}\text{Pr}[A_{i}]
$$

for general events:

$$
\text{Pr}\left[ \bigcup_{i=1}^{n}A_{i}\right]\le\sum_{i=1}^{n}\text{Pr}[A_{i}]
$$

**Inclusion-Exclusion Principle:** 

$$
\text{Pr}\left[ \bigcup_{i=1}^{n}A_{i}\right]=\sum_{l=1}^{n}(-1)^{l+1}\cdot \sum_{1\le i_{1} \le i_{2}\le n} \text{Pr}[A_{i_{1}}\cap\dots \cap A_{i_{l}}]
$$

**Conditional probability:**

$$
\text{Pr}[A|B] := \frac{\text{Pr}[A\cap B]}{\text{Pr}[B]} 
$$

**Theorem of total probability:**

Let $A_{1},\dots, A_{n}$ pairwise disjunct events and $B\subseteq A_{1}\cup \dots\cup A_{n}$, then:

$$
\text{Pr}[B] = \sum_{i=1}^{n}\text{Pr}[B|A_{i}]\cdot \text{Pr}[A_{i}]
$$


