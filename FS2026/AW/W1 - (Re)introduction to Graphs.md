#FS2026 #AW 

- Pay attention to what each concept means because each has like 10 different names

### k-Connected Graphs
- A graph is connected if there is a path between any two vertices
- k-connectedness describes the "intensity" of this connection
- Say you remove k vertices from a connected graph and it is no longer connected. The set of vertices removed is called a **separator**. In a k-connected graph, every separator has **at least** k vertices.
- Additionally, it must hold that $|V|\ge k+1$. 
- A **k-edge-connected** graph is defined analogously, only considering subsets of edges instead of vertices. 
	*See Def. 1.23 and 1.24 in the script (page 33)*
- An equivalent analysis of connectivity would be considering how many vertex-disjoint paths between any two vertices exist. 
	*See Satz 1.25 (Menger) in the script (page 34)*

### Special Case: k = 1
- In a 1-connected graph, there must exist (at least) one vertex such that removing it would disconnect the graph. Vertices with this property are called **cut vertices** (also articulation points).
- All cut vertices can be found in linear time using a modified version of DFS, whereby one notes two values. 
	- **DFS number:** number of the vertex in the order of visited vertices 
	- **low:** smallest DFS number that can be reached by taking any amount of DFS-edges and (in this order) and then one Rest-edge (no clue if that's the English name). 
- **Obs:** note that low can always be computed considering only the current vertex, since it is the minimum between vertices reached by all rest-edges and DFS-edges (one only needs to consider the first node in the DFS-path since the smallest value will propagate backwards). 
- Knowing this, we have that $v$ is a cut vertex if and only if:
	- $v$ is the root and has degree at least two, or
	- $v$ is not the root and there is $w \in V$ with $\{ v,w \}\in E$ and $\text{low}[w]\ge \text{dfs[v]}$.
- For any graph stored in an adjacency list, all cut vertices can be found in $O(|E|)$, the same holds for cut edges.
- An edge $e=\{ v,w \}$ is a cut edge if and only if $\text{low[w]}>\text{dfs}[v]$. 

### Block Decomposition
- We can separate connected graphs into **blocks**. These blocks are analogous to partitions of an equivalence relationship. The "intersection" between any two blocks is a cut vertex. 
	*See Def. 1.29 in the script (page 41)*
- The block decomposition is always:
	- bipartite
	- connected
	- acyclic
- Blocks will prove essential later to facilitate divide-and-conquer approaches. Say one wants to find the shortest path between two cities separated by a river and connected by a single bridge. One can be sure this path will be the shortest path from point A to one end of the bridge and the shortest path from the other end of the bridge to point B.  

### Cycles
- An **eulerian cycle** visits all edges exactly once and returns to the starting point. They can be efficiently calculated by running through the graph, finding cycles among unvisited edges and combining these cycles into one spanning the whole graph. 
- An eulerian cycle exists if and only if all nodes have even degree.
- They can be computed efficiently in $O(|E|)$ time.  
	*See page 43 in the script for descriptions and page 46 for pseudocode*
- A **hamiltonian cycle** visits all nodes exactly once and returns to the starting point. They cannot be calculated in polynomial time, as the problem is NP-Complete. 
- They can be computed in $O(n\cdot 2 ^{n})$ time, where $n = |V|$. Memory use can be optimized to be polynomial. 
- However, we can consider special cases, such as grid-graphs. A $m\times n$ grid contains a hamiltonian cycle if and only if $m$ or $n$ are even. We can prove this by separating nodes by their parity (like squares on a chessboard) and deriving a contradiction for the opposite case. 
- If $G=(A\uplus B, E)$ is bipartite with $|A|\not=|B|$, it cannot contain a hamiltonian cycle. 
	*See page 55 in the script for another example (hypercubes)*
