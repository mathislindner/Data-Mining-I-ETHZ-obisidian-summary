# l0 norm SVM
1. Train a regular linear SVM (using  $\ell_1$-norm or $\ell_2$-norm regularization). 
2. Re-scale the input variables $x$ by multiplying them by the absolute values of the components of the weight vector $w$ obtained, that is $x_new = w\odot x$. 
3. Iterate the first 2 steps until convergence.