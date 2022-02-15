# Soft Margin SVM
*Sometimes trying really hard not to misclassify one data point will result in worse seperability. Sometimes we can find better Support Vectors than the first ones at the Edge of the separation just like in [[Hard Margin SVM]]. That's why Soft Margin SVM exists*

- $C \in \mathbb{R}$ is the **penalty score parameter** that determines the tradeoff between maiximizing the margin and minimizing the margin errors
- $\xi$ is a **slack variable**, which measures the degree of **misclassification** of each margin error.
$$min_{w\in H,b\in \mathbb{R}, \xi \in \mathbb{R}}\frac{1}{2}||w||² + C\sum_{i=1}^n\xi_i$$
**subject to** 
$$y_i(<w,x_i>+b\geq- \xi_i,$$$$\forall i\in \{1,..,n\}:\xi_i\geq0)$$

![[Pasted image 20220213161032.png]]
## Alternative Soft-margin SVM
$\upsilon \in (0,1]$ 
$$min_{w\in H,b\in \mathbb{R}, \xi \in \mathbb{R}^n}\frac{1}{2}||w||² + (\frac{1}{n}\sum_{i=1}^n\xi_i) - \upsilon \rho$$
**subject to** 
$$y_i(<w,x_i>+b\geq \rho- \xi_i,$$$$\forall i\in \{1,..,n\}:\xi_i\geq0,\rho\geq0$$
- ν can be shown to be a lower bound for the fraction of support vectors and an upper bound for the fraction of margin errors among all training points.

## Class imbalance
- We should weigh the errors by how much data we have of each class since it would unfairly shift the hyperplane away:
- If we have more data we will have more errors, we need to take those into account in our #**penalty_score_parameter** $C^+ \space C^-$   
$$min_{w\in H,b\in \mathbb{R}, \xi \in \mathbb{R}}\frac{1}{2}||w||² + C^+\Sigma_{i|y_i=1}\xi_i+ C^-\Sigma_{i|y_i=-1}\xi_i$$