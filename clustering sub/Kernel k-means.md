# Kernel k-means
- It would be attractive to perform clustering using [[Kernel]]s 
	- Can move clustering problem to **different feature spaces** 
	- Can cluster **string and graph data** 
- But we have to be able to perform all steps in k-means using kernels!

The key step in k-means is to compute the distance between **one data point** $x_1$ and the mean of a cluster of points $x_2, . . . , xm$
$$||\phi(x_1)-\frac{1}{(m-1)}\sum_{j=2}^m\phi(x_j)||^2$$
$$=k(x_1,x_1)-\frac{2}{(m-1)} \sum_{j=2}^{m}k(x_1,x_j)+\frac{1}{(m-1)^2}\sum_{i=2}^m\sum_{j=2}^mk(x_i,x_j)$$
Thanks to: $d(x_i,x_j)^2 = ||\phi(x_i)-\phi(x_j)||^2 = k(x_i,x_i)-2k(x_i,x_j)+k(x_j,x_i)$  

## Silhouette coefficient
- A silhouette coefficient $s(x)$ (Rousseeuw, 1987) relates the average distance between a point x and and all others points from its cluster C, $d(x, µC )$, to the average distance between a point x and the other points from the second nearest cluster C' , $d(x, µC')$:
$$s(x)= \frac{d(x,\mu_C)-d(x,\mu_{C'})}{max(d(x,\mu_C),d(x,\mu_{C'}))}$$
- s(x) is close to 1, if a point is clearly located in cluster C
- s(x) is close to 0, if a point is located between two clusters
- s(x) is negative is it is closer to cluster C than its current cluster.

![[Pasted image 20220213193916.png]]![[Pasted image 20220213193935.png]]