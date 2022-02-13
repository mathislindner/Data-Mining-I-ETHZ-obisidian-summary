# Kernel on structured data
## R-convolutions kernels
- R-Convolution kernels are a famous recipe for constructing kernels on structured data. It is based on decomposing objects X and X' via a relation R into sets of substructures S and S' . 
- Their most simple and most widely used instance $k_R$ is the idea to compare all pairs of these substructures of X and X' pairwise $$k(X,X') = \sum_{s\in S, s'\in S'}k_{base}(s,s')$$
- For instance, a substructure would be the elements of a set, the nodes of a graph or the substrings of a string. 
- $k_{base}$ is an arbitrary vectorial kernel, very often even the #delta_kernel.

## String Kernels
- The spectrum kernel, mentioned above, counts all pairs of matching substrings in two strings. 
- That is, X and X' are strings and S and S' are the sets of all of their substrings.$$k_{R}(X,X') = \sum_{s\in S, s'\in S'}k_{base}(s,s')$$
- $k_{base}$ is a #delta_kernel, that is, for every pair of matching substrings, the kernel increases by one. 
- Naively, one has to enumerate all substrings (quadratic effort $O(|X|^2 + |X'| ^2 )$. 
- Via a special data structure called Suffix Trees, it can be done in linear time $O(|X| + |X' |)$  

## Kernels on graphs
### Random Walk Kernel
- Count matching walks in G and G' : the more **matching walks** there are, the higher the **similarity** between G and G' . 
- Matching walks are sequences of nodes and edges with **matching node labels**
### Elegant Computation
- Compute the direct product graph of G and G' and count all walks of length k in it.
-  Every walk in the product graph corresponds to one walk in G and in G':
$$k_{\times}(G,G')=\sum_{i,j=1}^{|V_\times|}[\sum_{k=0}^{\infty}\lambda^kA_{\times}^k]_{i,j} = e^T(I-\lambda A_{\times})^{-1}e$$

![[Pasted image 20220213185928.png]]