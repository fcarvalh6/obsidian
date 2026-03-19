#FS2026 #A 

A series is an expression of the form

$$
a_{0}+a_{1}+a_{2}+\dots = \sum_{i=0}^{\infty}a_{i}
$$

and the $a_{n}$ terms are elements of the series. The convergence of a series is the convergence of the partial sums, that is:

$$
a_{0}+a_{1}+\dots=\lim_{ n \to \infty }s_{n}=\sum_{k=0}^{\infty}a_{k} = L
$$

and $L$ is also called the value of the series. 

**Theorem:** if a series converges, the sequence of its terms is a zero sequence. 

**Lemma:** given two convergent series, the series of the sum of their terms is the sum of the individual series and the series of the terms multiplied by a constant is the series multiplied by a constant. 

**Lemma:** given an index $N$, the sum of the terms starting at $N$ converges if and only if the original series converges. In this case it also holds that

$$
\sum_{n=0}^{\infty} a_{n}=\sum _{n=0}^{N-1}a _{n}+ \sum_{n=N}^{\infty} a_{n}
$$

**Theorem:** say we have three series with terms $a_{n}, b_{n}, c_{n}$ such that $c_{n}\le b_{n}\le a_{n} \ \ \forall n \ge N$ 
- if series $a$ converges, so does series $b$
- if series $c$ diverges, so does series $b$

A series is **absolutely convergent** if the sum of the absolute value of the terms converges. 

A series is **conditionally convergent** if it converges and is not absolutely convergent.

**Theorem:** for a conditionally convergent series of real elements, there is a permutation of the elements such that any real number $L$ can be represented as the convergence of the series.

**Theorem:** for a conditionally convergent series of real elements, the permutation of elements will also converge to the same point. 

**Theorem:** Leibniz-Criterium, check script. 

The **Cauchy-Criterium** and **Triangle Inequality** can be extended to series. 

**Theorem (Root-Criterium):** let $(a _ {n}) _ {n\in \mathbb{N}}$ a sequence of real numbers and $\rho=\limsup _ { n \to \infty }(|a _ {n}|)^{1/n}$, then:
- if $\rho < 1$, the series given by summing $a_{n}$ converges
- if $\rho > 1$, the series given by summing $a_{n}$ does not converge

**Theorem (Quotient-Criterium):** let $(a _ {n}) _ {n\in \mathbb{N}}$ a sequence of real numbers with $a_{n}\not=0$ and $\rho=\lim _ { n \to \infty }\frac{|a _ {n+1}|}{|a _ {n}|}$, then:
- if $\rho < 1$, the series given by summing $a_{n}$ is absolutely convergent
- if $\rho > 1$, the series given by summing $a_{n}$ does not converge