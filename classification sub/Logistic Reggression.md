# Logistic Regression
[video to illustrate](https://youtu.be/yIYKR4sgzI8)
- Model for binary output variables: $y \in \{-1,1\}$ 
- Target variable $z = \sum_{i=1} w_ix_i+w_0$ 
$$f(z) = \frac{\exp(z)}{exp(z)+1}$$
![[Pasted image 20220213020727.png]]
$$
f_w(x) = f(<w,x>) = \frac{1}{1+exp(-(w_0+\sum_{i=1}^dw_ix_i))}
$$
- $f_w(x)$ is the probability that $x$ is in class 1
## Inverse of the logistic function 
$g = f^{-1}$ $$g(f_w(x))=\ln(\frac{f_w(x)}{1-f_w(x)})= w_0+\sum_{i=1}^dw_ix_i$$
## Training the model
- We need to find a way to train the weights $w_i$ 
- $\log(\frac{1}{1+exp(-y<w,x>)})$ = $-\log(1+exp(-y<w,x>))$ 
- Training means **minimizing** the total negative log probability of **all** points.
$$argmin_{w\in \mathbb{R^d}}\frac{1}{n}\sum_{i=1}^n\log(1+exp(-y_i<w,x_i>))$$
- To minimize the above function you can use a **Maximum Likelihood Estimation**

## Discussion
- Logistic regression models are easy to fit: The algorithms are easy to implement and fast.
- There are methods to train Logistic regression models that take time linear in the number of non-zero features in the data, which is the minimal possible time. 
- Logistic regression models are easy to interpret, as their output represents the log odd ratio between the positive and the negative class. 
- Several important extensions (multiclass classification, nonlinear decision boundaries, other types of output data) are possible.