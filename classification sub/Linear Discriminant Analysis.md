# Linear Discriminant Analysis
## Assumptions
- The goal is to predict a label $y ∈ \{0, 1\}$ from a vector x of d features, that is, $x = (x_1, . . . , x_d )$
- We assume that $P(Y = 1) = P(Y = 0) = \frac{1}{2}$ . 
- We assume that the conditional probability of X given Y is a multivariate Gaussian distribution. 
- The covariance matrix Σ is the same for both classes, Y = 0 and Y = 1, but they differ in their means, µ0 and µ1 .

## Log-likelyhood ratio
- The density distribution is
$$\mathcal{N}(x|\mu,\Sigma) = \frac{1}{(2\pi)^{\frac{d}{2}}|\Sigma^{\frac{1}{2}}|}e^{\frac{-1}{2}((x-\mu)^T\Sigma^{-1}(x-\mu))}$$
- Our goal is to find $argmax_{y \in \{0,1\}} P(Y=y)P(X=x|Y=y)$ 
- We predict $f(x)=1$ if the log-likelyhood ratio execeeds zero $$\log(\frac{P(Y=1)P(X=x|Y=1)}{P(Y=0)P(X=x|Y=0)})$$
which is equivalent to:
$$<w,x>+b = \sum_{i=1}^dw_ix_i+b$$
with $$w = (\mu_1- \mu_0)^T\Sigma^{-1}$$
and $$b = \frac{1}{2}(\mu_0^T\Sigma^{-1}\mu_0 - \mu_1\Sigma^{-1}\mu_1)$$
## Link to #linear_regression
- This shows that linear regression is a Bayes-optimal classifier under the aforementioned assumptions. 
- To perform LDA, all we have to do is to estimate µ0 , µ1 and Σ from the data, and use the equations above to determine w and b. 
- Then the classification is performed via $$f(x) = sgn(<w,x> + b)$$
- This mathematical elegance goes hand in hand with the difficulty to compute Σ−1 in very high-dimensional spaces.
