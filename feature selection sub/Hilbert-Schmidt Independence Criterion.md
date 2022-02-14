# Hilbert-Schmidt Independence Criterion
The larger the criterion, The larger the dependance.
## Definition
- The Hilbert-Schmidt Independence Criterion (HSIC) measures the dependence of two random variables X and Y . 
- An empirical estimate of the HSIC is proportional to
$$trace(KHLH)$$
	- K is a kernel matrix on X, 
	- L is a kernel on Y , 
	- H is a centering matrix with $Hij = δ(i, j) − \frac{1}{n}$ 
	- $HSIC(X, Y ) = 0$ iff X and Y are **independent**. The **larger** $HSIC(X, Y )$, the larger the **dependence** between X and Y
