# Distance Functions
A distance function accepts the [[Metrics]] Definition

## Popular Distance functions
$$x,x' \in \mathbb{R}^d$$
- Manhattan Distance $$d(x,x') = \sum_{i=1}^d |x_i-x_i'|$$
- Hamming Distance (on binary vectors)$$d(x,x') = \sum_{i=1}^d |x_i-x_i'|$$
- Euclidean Distance $$d(x,x') = \sqrt {\sum_{i=1}^d(x_i-x'_i)^2} $$
- Chebyshev Distance $$max_i(|x_i-x_i'|)$$
- Minkowski Distance $$d(x,x') = (\sum_{i=1}^d|x_i-x_i'|^p)^{1/p}, p \in \mathbb{R}^+ $$
- The #Mahalanobis_distance $d_M$ takes the $d \times d$ covariance structure $\Sigma$ between features into account: [Video to illustrate](https://youtu.be/spNpfmWZBmg)
$$d_M(x,x) = \sqrt{(x-x')^{T} \Sigma^{-1}(x-x') }$$
	- where the covariance Matrix is defined as $$\Sigma_{ij} = cov(X_i,X_j) = \mathbb{E}[(X_i-\mu_i)(X_j-\mu_j)]$$
	- $X_i$ being a random variable representing feature i and $\mu_i$ is its mean