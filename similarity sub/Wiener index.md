# Wiener Index
- Let $G(V,E)$ be a graph of Vertices $V$ and Edges $E$
- Let $P$ be the set of shortest paths in $G$ (which can be found with the #Floyd-Warshall Algorithm) and $l(p)$ it's length.
**Then** the Wiener index is as follows
$$v(G) = \frac{1}{|P|} \sum_{p \in P} l(p)$$
It is the sum of the all the shortest Paths divided by the number of paths.