# Similarity on nodes

## Shortest path distance
- Objects are $n$ nodes in a graph G
- weights $w(i,j)$
- shortest path length is the most popular distance function
- #Floyd-Warshall's algorthm computes **all pairs-shortest paths** in $O(n³)$
![[Pasted image 20220212171548.png]]

$$  
\begin{algorithm}[H]
\KwData{Distance matrix $D$}
\KwResult{Shortest path matrix $D$}
\SetAlgoLined
 \For{k in $[n]$}{
  \For{i in $[n]$}{
  \For{j in $[n]$}{
    $D_{ij} = \min (D_{ij}, D_{ik} + D_{kj})$
  }}
  }
 
 \caption{Floyd-Warshall algorithm}
\end{algorithm}$$

