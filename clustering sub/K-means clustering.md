# K-Means Clustering
[video](https://youtu.be/4b5d3muPQmA)
## Objective
Partition the dataset into k *clusters* such that the **intra-cluster** variance is **minimised**
$$V(D) = \sum_{i=1}^k\sum_{x_j \in S_i}(x_j-\mu_j)^2$$
- $V$ is the Variance
- $S_i$ is a Cluster
- $\mu_i$ is its mean
- $D$ is the dataset of all points $x_j$

##  Lloyds algorithm
1) Partition the data into k initial clusters 2
2) Compute the mean of each cluster 
3) Assign each point to the cluster whose mean is closest to the point
4)  If any point changed its cluster membership: Repeat from Step 2)

## Similar algorithms
- [[K-Medoid]]
- [[Kernel k-means]]

## Moreover
- initialization has a **Huge impact**, so we should try different inits and compare them
- k-means is still the state-of-the-art method for most clustering tasks 
- When proposing a new clustering method, one should always compare to k-means. 
- Lloyds’ algorithm has several setbacks
	- It is order-dependent. (k)
	- Its results depends on the initialisation of the clusters. 
	- Its result may be a **local optimum**, not the global optimal solution. It is a greedy allgorithm

