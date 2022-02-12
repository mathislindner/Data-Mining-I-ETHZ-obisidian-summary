# Distance Functions
A distance function accept the [[Metrics]] Definition

## Popular Distance functions
$$x,x' \in \mathbb{R}^d$$
- Manhattan Distance $$d(x,x') = \sum_{i=1}^d |x_i-x_i'|$$
- Hamming Distance (on binary vectors)$$d(x,x') = \sum_{i=1}^d |x_i-x_i'|$$
- Euclidean Distance $$d(x,x') = \sqrt {\sum_{i=1}^d(x_i-x'_i)^2} $$
- Chebyshev Distance $$max_i(|x_i-x_i'|)$$
- Minkowski Distance $$d(x,x') = (\sum_{i=1}^d|x_i-x_i'|^p)^{1/p}, p \in \mathbb{R}^+ $$