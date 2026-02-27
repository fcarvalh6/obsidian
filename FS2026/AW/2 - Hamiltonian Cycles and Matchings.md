#FS2026 #AW 

### More on hamiltonian cycles
- Dirac: every graph with $|V|\ge 3$ and $\text{deg(v)}\ge \frac{|V|}{2} \forall v \in V$
	- The proof uses the fact that, because of the minimal degree condition, there must be intersections which allow us to take the "longest path" (assuming the graph is not hamiltonian), turn it into a cycle, and generate an even larger path. This is a contradiction to the fact the path was supposed to be the longest. These intersections can be derived using the inclusion/exclusion principle. 
- Inclusion/Exclusion principle:
	- Think of a venn-diagram, when counting sets, intersections end up being counted multiple times, so they have to be subtracted. 
	- $n=2:$ 

$$
|A_{1}\cup A_{2}| = |A_{1}|+|A_{2}|-|A_{1}\cap A_{2}|
$$

### Finding hamiltonian cycles efficiently (?)
- Naive algorithm runs in $O(n!)$
- Using DP, we can solve the problem in $O(n^{2}\cdot 2 ^{n})$
	- The algorithm is centered around 1-x-paths, and in the end we can see if it is possible to connect 1 to one of its neighbors going through all nodes in the graph. 
- Geht es besser? Probably not. This problem is **NP-Complete**.


### Traveling Salesman Problem (TSP)
- Also NP-Complete because we can write this as a variation of the hamiltonian cycle problem. 
- **Metric TSP** is a variation wherein the triangle inequality holds. There is a 2-approximation for this case centered around doubling a MST and taking shortcuts whenever possible.

### Matchings
- A subset of edges is a matching if no node in the graph is incident to more than one edge in the subset. This means $\varnothing$ is a matching. 
- A node is covered by a matching if there is an edge in the matching that contains it. 
- A **perfect** covers every node with exactly one edge. ($|M|=\frac{|V|}{2}$)
- In an **inclusion maximal** matching, adding any edge would make the subset not be a matching anymore)
- A **cardinality maximal** matching is a matching with most edges.  

### Finding matchings
- The greedy algorithm delivers an inclusion maximal matching which has at least half the edges of a cardinality maximal matching.
- An **augmenting** path for a matching $M$ starts and ends in nodes not covered by $M$ and takes alternating edges (one not in $M$, one in $M$, etc.). We can increase $M$ by taking this path and simply swapping the edges (ones not in $M$ are added to $M$ and vice versa). 
- Berge: every matching which isn't cardinality maximal has an augmenting path.
- We can thus use augmenting paths to start with any matching and increase it to a cardinality maximal. 
- Marriage theorem: a bipartite graph $G = (A\uplus B, E)$has a matching of size $|A|$ if and only if, for every subset $X$ of vertices of $A$, this subset has more neighbors than members. 