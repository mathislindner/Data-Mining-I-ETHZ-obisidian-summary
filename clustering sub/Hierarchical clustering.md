# Hierarchical clustering
If clusters have *subclusters*, we should use Hierarchical clustering
![[Pasted image 20220214105633.png]]
## Advantages
- Its clustering reflects the entire structure of the dataset
## Disadvantages
- It is **difficult** to make a clear statement about cluster membership in hierarchical clustering, as each point belong to a hierarchy of clusters. 
- Stopping Hierarchical Clustering early is an approach to circumvent this cluster-assignment problem. These criteria could be to **stop the merging of clusters** 
	- once a pre-defined number of **clusters k** has been reached. 
	- once the distance between the **closest** clusters exceeds a threshold $\epsilon$. 
## Concept
- Iteratively join the two most similar clusters [[Similarity]]
	- Single Link $s(C_i,C_j) = min_{x\in C_i,x'\in C_j}d(x,x')$ 
	- Average Link $s(C_i,C_j) = \frac{1}{|C_i||C_j|} \sum_{x\in C_i,x'\in C_j}d(x,x')$
	- Complete Link $s(C_i,C_j) = max_{x\in C_i,x'\in C_j}d(x,x')$ 

## Algorithm
![[Pasted image 20220214110106.png]]
## Moreover
![[Pasted image 20220214110129.png]]