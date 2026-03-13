#FS2026 #AW 

In a bipartite graph, every edge goes between two disjunct sets of vertices. We can expand this concept to higher amounts of disjunct sets such that no edge leaves and arrives at a vertex of the same set. These are colorings. 

A coloring is a map from the vertex set to a natural number such that no edge goes between nodes of the same number. Different graphs can be colored in different ways and with different amounts if colors. We call the minimum amount of colors to color a graph its *chromatic number*, or $\chi(G)$. Returning to the idea of bipartite graphs, we can say a graph is $\chi(G)-$partite, since we can assign a disjunct set of vertices to each color. 

**Theorem:** $G=(V,E)$ is bipartite if and only if it has no cycle of odd length as subgraph. 
- If there are no cycles of odd length, simply running BFS will result in a correct coloring.

**Theorem:** every map has a 4-coloring. 
- The question "Given $G$, is $\chi(G)\le 3$" is NP-Complete

A simple algorithm to find a coloring would to simply assign to each vertex the smallest number not present in any of its neighbors. This is the **greedy algorithm**. The amount of colors used by this algorithm is highly dependent on the order in which vertices are processed, but we know it can be, at worst, the maximum degree of a node in $G$ plus one (the color used to color the node proper). 

**Theorem:** $\chi (G)\le C(G) \le \Delta(G)+1$. $C(G)$ is the number of colors used by the greedy algorithm and $\Delta(G)$ is the highest degree in the graph. Coloring is found in $O(|E|)$ if $G$ is stored in an adjacency list. 

**Theorem (Brooks):** If $G=(V,E)$ connected, $G\not= K_{n}$ and $G\not=C_{2n+1}$, then $\chi (G)\le\Delta(G)$.
- and we can find a coloring in $O(|E|)$ which uses $\Delta(G)$ colors.

**Theorem:** $G=(V,E)$, $k\in \mathbb{N}$ with the property that every induced subgraph of $G$ has a node of degree at most $k$, then $\chi(G)\le k+1$ and we can find a $k+1-$coloring in $O(|E|)$.

**Theorem (Mycielski-Construction):** for every $k\ge 2$ there is a graph $G_{k}$  with no triangles such that $\chi(G_{k})\ge k$.

**Theorem:** every 3-colorable graph $G=(V,E)$ can be colored in time $O(|E|)$ with $O(\sqrt{ |V| })$ colors. 
- this is the case because for every node, the subgraph induced by its neighbors is bipartite, so a coloring can be found in linear time. 
- after a certain point, use Brooks. 