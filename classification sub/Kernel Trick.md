# Kernel Trick

The “kernel trick” allows to turn parametric, linear algorithms into non-parametric, non-linear algorithms by substituting inner products hxi , xji by a kernel function $k(x_i , x_j) = hφ(x_i), φ(x_j )$i without ever needing to explicitly evaluate the mapping φ(x). The “kernel trick”


We can choose any [[Kernel]] for SVM hard margin cross product in $$maximise_{\alpha \in \mathbb{R}^n} \sum_{i=1}^n\alpha_i - \frac{1}{2}\sum_{i,j=1}^n \alpha_i\alpha_jy_iy_j<x_i,x_j>$$
$$<x_i,x_j>_H = k(x_i,x_j)$$