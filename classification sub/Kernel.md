# Kernel
## Definition
- $x \in \mathbb{R}$ are mapped to a space $H$ via a mapping function:$$\phi :\mathbb{R} \rightarrow H$$
- Then the kernel us defined as an inner product $<\cdot \space, \space \cdot>: H\times H \rightarrow \mathbb{R}$ between data points in this space $H$:
$$k(x,x') = <\phi(x),\phi(x')>$$
## In Practice
We use kernels by
1) Proposing a kernel function and explicitly defining the corresponding mapping φ or/and
2) Combining known kernels in ways that obey the closure properties of kernels.
**Knowing these closure properties and a set of basic kernel functions is of utmost importance when working with kernels in practice.**

## Closure properties
$\forall k_1,k_2$ being kernels
$k$ is also a kernel with:

- $k = k_1+k_2$
- $k = k_1 \cdot k_2$ 
- $k = \lambda k_1, \space \lambda \in \mathbb{R}$ 
- if k is a kernel only defined on a set $D$. Then the zero Extension $k_0$ is also a kernel: 
		- $k_0(x,x') = k(x,x') \space if \space x \in D \space and \space x' \in D$ 
		- else $k_0(x,x') = 0$  
## Kernel examples
### Linear Kernel$$k(x,x') = \sum_{l=1}^dx_lx_l' = x^T\cdot x'$$
### Polynomial Kernel $$k(x,x') = (x^Tx'+c)^d \space c,d \in\mathbb{R}$$
### Gaussian Radial Basis Function (RBF) Kernel $$k(x,x') = exp(-\frac{1}{2\sigma²}||x-x'||^2)$$

### Constant 1 kernel $$k(x,x') = 1$$
### delta Dirac kernel 
#delta_kernel 
$$k(x,x') = 1, \space if \space x=x' $$
else $$k(x,x') = 0$$
[[Kernels on specific data]]