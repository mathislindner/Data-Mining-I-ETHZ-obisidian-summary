# Hard Margin SVM
$$min_{w\in H,b\in \mathbb{R}}\frac{1}{2}||w||²$$**subject to** 
$$y_i(<w,x_i>+b\geq1,\forall i\in \{1,..,n\})$$

- The size of the margin is $\frac{2}{||w||} \Rightarrow$ we try to minimise the function above, because the smaller $||w||$, the larger the margin, which is the thing we want to maximise to separate the planes.
-   **Why**: $y_i(<w, x_i> + b)\geq 1$?  
	$\rightarrow$Ensures that all training data points of the same class are on **the same side** of the hyperplane and **outside the margin**

## Optimization
- The solution vector w, the crucial parameter of the SVM classifier, has an expansion in terms of the training points and their labels. 
- Those training points with $αi > 0$ are the #Support_Vectors.

- To optimize the Hard-Margin we form the #Lagrangian
$$L(w,b,\alpha) = \frac{1}{2}||w||^2-\sum_{i=1}^n\alpha_i(y_i(<x_i,w>+b)-1)$$
- The Lagrangian is then minimised with respect to the primal variables $w$ and $b$ and maximised with respect to the dual variables $\alpha_i$ 
- At optimality $$\frac{\partial}{\partial b}L(w,b,\alpha)=0$$
$$\frac{\partial}{\partial w}L(w,b,\alpha)=0$$
such that: $\sum_{i=1}^n \alpha_i y_i= 0$ and $w=\sum_{i=1}^n \alpha_i y_i x_i$ 

## The dual Problem
Plugging the above equation into the Lagrangian: we get
$$maximise_{\alpha \in \mathbb{R}^n} \sum_{i=1}^n\alpha_i - \frac{1}{2}\sum_{i,j=1}^n \alpha_i\alpha_jy_iy_j<x_i,x_j>$$
$$\forall i \in \{1,...,n\}:\alpha_i\geq 0$$
Here The [[Kernel Trick]] comes into play!

We now find that we can use SVM's with
$$f(x) = sgn(\sum_{i=1}^ny_i\alpha_ik(x,x_i)+b)$$