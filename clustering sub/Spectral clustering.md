# Spectral Clustering
## Concept
- Spectral Clustering connects graph-based clustering with [[K-means clustering]]. 
- The difference is that we induce cut-based clustering
![[Pasted image 20220213234844.png]]

## Cut-based clustering 
- Objects are nodes in a graph G with nodes V and edges E. 
- The #adjacency_matrix W represents the similarities between pairs of nodes. Assume V is partitioned into k subsets: $V = \{C1, . . . , Ck \}$. 
- Cut-based clustering tries to minimize the total weight of inter-cluster edges
$$\min \frac{1}{2}\sum_{a=1}^{k}\sum_{b=1}^{k}\kappa(C_a,C_b)$$
where $\kappa (C_a,C_b) = \sum_{v_i \in C_a, v_j \in C_b, a\neq b}W_{ij}$ and $\kappa (C_a,C_b)=0$   

## Derivation from graph Laplacian to spectral clustering
- To define spectral clustering we also need [[Graph Laplacian]]
![[Pasted image 20220214093735.png]]
![[Pasted image 20220214093805.png]]
**It follows that finding the minimum k-cut is identical to minimizing**$$\sum_{a=1}^{k}c_a^TLc_a$$
This leads us to [[Spectral Clustering  Link to Eigenvalues and Eigenvectors]]

## Concept
- Spectral Clustering solves this problem pragmatically by using the vectors ua as a new representation of the data points and applying k-means to this new representation after normalization. 
- The new representation is $U = (u_n, u_{n−1}, . . . , u_{n−k+1})$, a $n × k$ matrix. 
- It is normalized row-by-row to obtain the new k-dimensional representation
$$Y= (y_1,...,y_n)^T$$
with $$y_i = \frac{1}{\sqrt{\sum_{j=1}^g}u^2_{i,n-j+1}}(u_{i,n},u_{i,n-1},...,u_{i,n-k+1})^T$$
## Algorithm
![[Pasted image 20220214101643.png]]

## Complexity 
- The overall worst case runtime is $O(n^3 )$ due to the need to compute eigenvectors and eigenvalues. 
- For sparse graphs with m edges, this runtime can be improved to O(mn). 
- Running [[K-means clustering]] requires a runtime in $O(tnk)$, where $t$ is the number of iterations of k-means until convergence. $O(nk)$ is the effort to compute the distance between all n points and k cluster means in each iteration.