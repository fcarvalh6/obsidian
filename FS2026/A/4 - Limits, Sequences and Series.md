#FS2026 #A 

**Vocab:** Folge is a sequence, Reihe is a series

**Sandwich Theorem:** find smaller and bigger functions and show both have the same limit. For example, take $(2^{n}+3^{n})^{1/n}$. 
- $(2^{n}+3^{n})^{1/n}\ge(3^{n})^{1/n}$ which tends to $3$ as $n\to \infty$ 
- $(2^{n}+3^{n})^{1/n}\le(2\cdot 3^{n})^{1/n}=2^{1/n}\cdot 3$ which also tends to $3$. 

### Functions and Sequences 

**Bounded/Monotonic Functions**
- A function can have an upper and lower bound. If it has both, it is **bounded**. 
- A function can be monotonic increasing/decreasing if values always grow/fall with larger indices.
- A sequence is a special kind of function represented by an ordered list of numbers where each element has a specific index in the sequence. 

**Lemma:** every bounded and monotonic function converges. This can be seen by considering that it must forever increase/decrease while also not surpassing the bounds.

**Lemma:** every convergent sequence is bounded. 

**Theorem:**
1. A monotonic sequence of real numbers converges if and only if it is bounded.
2. If $(a_{n})_{n\in \mathbb{N}_{0}}$ is monotonic increasing, it holds $\lim_{ n \to \infty }a_{n}=\text{sup}\{ a_{n}\mid n \in \mathbb{N}_{0} \}$
3. If $(a_{n})_{n\in \mathbb{N}_{0}}$ is monotonic decreasing, it holds $\lim_{ n \to \infty }a_{n}=\text{inf}\{ a_{n}\mid n \in \mathbb{N}_{0} \}$

### Limit Inferior/Superior

$$
\limsup_{ n \to \infty } a_{n}=\lim_{ n \to \infty } \text{sup}\{ a_{k}\mid k \ge n \}  
$$

$$
\liminf_{ n \to \infty } a_{n}=\lim_{ n \to \infty } \text{inf}\{ a_{k}\mid k \ge n \}  
$$

- The limit superior/inferior is the infimum/supremum of all suprema/infima when $k\to \infty$.
- If a sequence converges, its limit, limit superior and limit inferior are the same.
- A bounded sequence converges if and only if the three limits coincide. 

Limit superior/inferior describe greatest/smallest possible accumulation points.

**Lemma:** every bounded series of real numbers has an accumulation point and a convergent subsequence. 

### Cauchy-Sequences

A sequence is a Cauchy-Sequence if $\forall \varepsilon>0 \ \exists N$ s.t. $\forall m,n\ge N \ |a_{n}-a_{m}|<\varepsilon$. Basically, there will be a certain point such that the difference between any two numbers is infinitely small. 

**Lemma:** every Cauchy-Sequence is bounded. Moreover, a sequence of real numbers only converges if it is a Cauchy-Sequence. 