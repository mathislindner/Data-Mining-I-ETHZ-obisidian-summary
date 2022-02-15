# Naive Bayes
Bayes' Rule
$$
P(Y=y|X=x) = \frac{P(X=x|Y=y)P(Y=y)}{P(X=x)}
$$
X is the random variable that describes the #features, Y the random variable that describes the class label

## Naive Bayes Classification
## Advantages
- Speed: effort for one test point is $O(md)$, as we have to compute the class posterior $\forall m$ classes
- Ability to deal with missing data: Missing features xj can simply be dropped when evaluating the class posteriors, by dropping $P(x_j |y_i)$. 
- Ability to combine discrete and continuous features: Use discrete or continuous probability distributions for each attribute 
- Practical performance: Despite the unrealistic independence assumption on the features, Naive Bayes often provides good results in practice.

[Video to illustrate the concept](https://youtu.be/O2L2Uv9pdDA)
Classify $x$ into one of $m$ classes $y_1,...,y_m$

$$
argmax_{y_{i}}P(Y=y|X=x) = argmax_{y_{i}}\frac{P(X=x|Y=y)P(Y=y)}{P(X=x)}
$$
- $P(Y=y_i)$ is the prior probability
- $P(X = x)$ is the evidence
- $P(X=x|Y=y_i)$ is the likelyhood
- $P(Y=y_i|X=x)$ is the posterior probabilty

## Simplification
- $P(Y=y_i|X_x) \space ∝ \space P(Y=y_i)P(X=x, Y=y_i)$  since $P(X=x)$ is the same for all classes
-  If $x$ is multidimensional $\rightarrow$ $x = (x_1,...,x_d)$ we further assume that the features are **conditionally independent** given the class label 
$$
P(X=x|Y=y_i) = P(X=(x1,...,x_d)|Y=y_i)= \prod_{j=1}^dP(X_j=x_j|Y=y_i)
$$
## The actual classification
$$
argmax_{y_{i}}P(y=y_i|X=x) ∝ P(Y=y_i)\prod_{j=1}^dP(X_j=x_j|Y=y_i)
$$
## Train the model
- One has to estimate $P(Y)$. 
	- Typically, one assumes that all classes have the **same probability**, or one infers the class probabilities from the **class frequencies** in the training dataset. If we already have alot of one label in the test set, then the new data is probably also as likely to be from that one.
- One also has to estimate P(X|Y) for $x = (x_1,...,x_d)$
	- binary data: $P(X=x|Y=y_i) = \prod_{j=1}^d Ber(x_j|\theta{j,i})$ 
		- $\theta{j,i}$ being the **probability** that feature $x_j$ has value 1 in class $y_i$
	- continuous data: $P(X=x|Y=y_i) = \prod_{j=1}^d \mathcal{N}(x_j|\mu_{j,i},\sigma_{j,i}^2)$ 
		- $\mu_{j,i}$ being the **mean** of feature ( #features)  $x_j$ in objects of class $i$ and $\sigma_{j,i}^2$ is the **variance**

- Bernoulli distribution: 
	- $Ber(x|\theta) = \theta \space\text{, if x=1}$ 
	- $Ber(x|\theta) = 1- \theta \space\text{, if x=0}$ 

- Gaussian (normal distribution) $\mathcal{N}(x|\mu,\sigma^2) = \frac{1}{\sqrt{2 \pi \sigma^2}}e^{\frac{-1}{2\sigma^2}(x-\mu)}$
[video](https://youtu.be/H3EjCKtlVog)

$$
\mathcal{N}(x|\mu,\Sigma) = \frac{1}{(2\pi)^{\frac{d}{2}}|\Sigma^{\frac{1}{2}}|}e^{\frac{-1}{2}((x-\mu)^T\Sigma^{-1}(x-\mu))}
$$
