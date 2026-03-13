#FS2026 #A 

### Sequences
- A sequence is an endless list of numbers, where every number is called a member of the sequence.
- It can also be described as a function $f: \mathbb{N}_{0}\to \mathbb{R}$ or $f: \mathbb{N}\to\mathbb{R}$. $\mathrm{Im}(f)$ contains all elements of the sequence. 

A sequence is **convergent** if there is an $L\in \mathbb{R}$ such that:

$$
\forall \varepsilon >0 \ \exists N > 0 \ \text{so dass} \ \forall n>N:|a_{n}-L| < \varepsilon
$$

$L$ is also the limit described as $\lim_{ n \to \infty }a_{n}=L$. If there is no $L$ with this property, then the sequence is divergent. 

**Special cases:** diverge towards infinity and minus infinity, check slides.

### Subseries
- For a sequence $(a _ {n}) _ {n\in \mathbb{N} _ {0}}$ a subsequence is a sequence of form $(a_{n_{k}})_{k\in \mathbb{N}_{0}}$, where $n_{k}$ is a sequence of ascending non-negative numbers. 

### Accumulation Point
- Point that will always come again in the series in a certain interval
- A is an accumulation point if and only if a convergent subsequence has limit A
- A convergent sequence has only one accumulation point, which is also its limit
- If A is an accumulation point, there is an infinite number of points in any interval of allowed deviation $\varepsilon>0$. 

### Limits
- Summing and multiplying functions has some interesting effects on limits. 
- It is important to know a couple of important limits.
- Both of these on SW3, Folgen.pdf