# Classification
## Definition
- Given an object, which class of objects does it belong to
- Given *$x$, predict class $y$

## Examples
- Computer vision: Is this object a chair
- Credit cards: Can this customer be trusted?
- Function prediction: Is this protein an enzyme?

## Setting
- Classification can be supervised ( #supervised_learning ) or unsupervised ( #unsupervised_learning )
- A training dataset is a dataset of pairs $\{ {({x_i} ,y_i}) \}^n_{i=1}$  that is objects $X$ and their respective label $Y$
- $x_i \in \mathbb{R}^n$ and $y_i \in  labels$
- The test set is dataset of test points $\{x_i\}_{i=1}^d$ 
- The task is to predict the class lavel $y_i'$ of  $x_i'$ via a **function** f

## Labels of Y
- if $y \in \{0,1 \}$ We have #binary_classification
- if $y \in \{1,...,n \}$  with $n \geq 3$  and  $n \in \mathbb{N}$  We have #multiclass_classification
- if $y \in \mathbb{R}$ we have a #reggression problem

[[Evaluating Classifiers]] is a huge part of Classification

## Ways to Classify
[[Nearest Neighbour Classification]]
[[Naive Bayes]]
[[Linear Discriminant Analysis]]
[[Logistic Reggression]]
[[Descision Tree]]
[[Support Vector Machines]]