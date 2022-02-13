# K-Medoid
- It is considered the brother of k-means
- Don’t use the mean of each cluster but the **medoid**. 
- The medoid is the point closest to the mean: $$m_i = argmin_{xj∈S_i} ||x_j − µ_i ||^2$$
-  One thereby restricts the cluster ‘means’ to points that are present in the dataset. 
- One only minimises variance with respect to these points.