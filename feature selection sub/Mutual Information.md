# Mutual Information
- Given two random variables X and Y , we define the mutual information $I(·, ·)$ as
$$I(X,Y)=\sum_{y\in Y}\sum_{x\in X}p(X=x,Y=y)\log(\frac{p(X=x,Y=y)}{p(X=x)(Y=y)})$$
- X is the input variable, 
- Y is the output variable, 
- $p(X = x, Y = y)$ is the (joint) probability of observing x and y, 
- $p(X = x)$ and $p(Y = y)$ are the marginal probabilities of observing x and y, respectively. 
- log is usually the logarithm with base 2.