# Nearest Neighbour
The Predicted label $y_i$ of $x_i$ is the point closest to it: *Nearest neighbour* 
$$
x_i = arg \space min_{x' \in D} ||x-x'||^2 \Rightarrow f(x) = y_i
$$

## k-NN Classification
- An object is classified to the class most common among its k nearest neighbors (k ∈ N). If k = 1, then the object is assigned to the class of its single nearest neighbor. 
- k is a hyperparameter that is chosen by the user.
- The larger k, the lower the influence of single noisy points on the classification. In binary classification problems, one usually chooses odd k to avoid ties. 
- It is an instance of instance-based learning and lazy learning.
- It's runtime is $O(n + n \log n)$
	- $O(n)$ to find the nearest neighbour in 1-NN
	- so for k nearest neighbours we have the formula above

## k-NN Challenges:
- Speed of prediction 
- Choice of #hyperparameter k 
- Choice of [[Distance Functions]] and weights of dimensions

## Subtleties
### Triangular inequality
- Exploit the #triangle_inequality because it holds for any [[Metrics]]
- Rewriting the inequality gives us:
$$d(x1,x2) \geq d(x1,x3) + d(x2,x3)$$
- In other words: we can get a lower bound for $d(x1,x2)$ if we know the right hand side of the equation $\Rightarrow$ you can avoid computing  $d(x1,x2)$ 
### #hyperparameter k
- #cross-validation  on the training data
- Bootstrapping on training data 
	- Split the training dataset in two subsets T1 and T2. 
	- For different choices of k, compute the accuracy on T2, using T1 as training set. 
	- Repeat the above two steps several times. 
	- Pick the k with the highest average accuracy across all iterations.
### Weigh the dimensions
- The #Mahalanobis_distance $d_M$ takes the $d \times d$ covariance structure $\Sigma$ between features into account, so we can use it for k-NN 