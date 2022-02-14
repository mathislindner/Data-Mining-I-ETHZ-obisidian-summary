# Spectral Clustering Eigenvalues and Eigenvectors
## Ratio Cut
- Minimum k cut clustering is prone to finding very **small clusters**. 
- **Ratio Cut** accounts for this problem by dividing the cut size by the size of the cluster
$$min_{C}\sum_{a=1}^k\frac{1}{|C_a|}\sum_{b=1}^k\kappa(C_A,C_b)$$
$$min_C\sum_{a=1}^k\frac{c_a^TLc_A}{||c_a||^2}$$
- Finding the optimal C, that is the optimal binary cluster indicator vectors ca for $a ∈ \{1, . . . , k\}$, is NP-hard. 
- We therefore relax the solution and allow the vectors ca to take any real value, rather than being binary. $$\sum_{a=1}^k(\frac{c_a}{||c_a||})^TL(\frac{c_a}{||c_a||}) = \sum_{a=1}^ku_a^TLu_a \space(8)$$
$u_a = \frac{c_a}{||c_a||} \space , c_a \in \mathbb{R}$  

## Lagrange multipliers
- To find the optimal u, we first incorporate the constraint $u_a^T u_a = 1$ via a Lagrange multiplier $λ_a$
$$\sum_{a=1}^{k}u_a^TLu_a+\sum_{a=1}^{k}\lambda_a(1-u_a^Tu_a)$$
- Now setting the derivative to 0 to find a minimum
$$\frac{\partial}{\partial u_i}(\sum_{a=1}^{k}u_a^TLu_a+\sum_{a=1}^{k}\lambda_a(1-u_a^Tu_a))
\overset{!}{=}0$$
$$2Lu_i-2\lambda_iu_i=0$$
$$Lu_i=\lambda u_i$$
- **This implies that all u are eigenvectors of L**
- $$\Rightarrow u_a^TLu_a=u_a^T\lambda_au_a = \lambda_a$$
- This in turn implies that in order to minimize Objective (8), one should choose the **k smallest eigenvalues** of L and their corresponding eigenvectors. 
- The eigenvectors represent the **relaxed cluster indicator vectors** (excluding $u_n$)