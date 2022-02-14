# Expectation Maximization clustering
also called soft [[K-means clustering]]
## Introduction
- k-means is based on a hard assignment of points to clusters. 
- Wouldn’t it be more realistic to work with the probabilities of each point to belong to each cluster rather than a hard assignment? 
- This is the core idea of Expectation Maximization (EM) 
- Clustering with a Mixture of Gaussian distributions. 


- We are dealing with **observed variables** (objects X and their features) and latent variables (the cluster membership of the objects Y ), and **model parameters $θ$** (parameters of the underlying probability distribution). 
- We would like to maximize $p(X|θ)$.
- This optimization is difficult as $$\log p(X|\theta) = \log\{\sum_Yp(X,Y|\theta)\}$$
- That is, we have to sum over the **latent variables** inside the logarithm, which makes the evaluation of the maximum likelihood **extremely challenging**.

## Algorithm
- **Given a joint distribution p(X, Y |θ) over observed variables X and latent variables Y , governed by parameters θ, the goal is to maximize the likelihood function p(X|θ) with respect to θ**
1) Choose an initial setting for the parameter $\theta^{old}$ 
2) Expectation step (E step): Evaluate $p(Y |X, θ^{old} )$. 
3) Maximization step (M step): Evaluate θ new given by
$$\theta^{new} = argmax_{\theta} \mathcal{Q}(\theta,\theta^{old})$$
where $\mathcal{Q}(\theta,\theta^{old})= \sum_Yp(Y |X, θ^{old})\log p(X,Y|\theta)$ 
4) Check for **convergence** of parameters or log likelihood. If **not converged**, then 
$$θold ← θnew$$ and return to Step 2

## Concept
- Consider the case of a mixture of k Gaussians in which $\theta$ is a triplet $(c,\{ \mu_1,... \mu_k \} , \{ \Sigma_1,...\Sigma_k \})$ 
- Where $P_\theta[Y=y] = c_y$ 
$$P_{\theta(t)}[X=x,Y=x] = \mathcal{N}(x|\mu_y,\Sigma_y) =\frac{1}{(2\pi)^{d/2}|\Sigma_y|^{1/2}}exp(-\frac{1}{2}((x-\mu_y)^T)\Sigma_y^{-1}(x-\mu_y))$$
- For simplicity: $\Sigma_1 = \Sigma_2 = ... =\Sigma_k = I$ , $I$ being the identity Matrix

## Expectation Step 
![[Pasted image 20220214105109.png]]

## Maximisation Step
![[Pasted image 20220214105148.png]]

- The Maximal $c$ can be shown to be:
$$c_y = \frac{\sum_{i=1}^nP_{\theta(t)}[Y=y|X=x_i]}{\sum_{y'=1}^k\sum_{i=1}^nP_{\theta(t)}[Y=y'|X=x_i]}$$
## Moreover
- [[K-means clustering]] assigns each point to a cluster according to the distance to the cluster means. Then the cluster means are updated based on the examples in this cluster. 
- EM determines the **probability** that each example belongs to each cluster. Then the cluster means are updated based on a **weighted sum** over all data points.