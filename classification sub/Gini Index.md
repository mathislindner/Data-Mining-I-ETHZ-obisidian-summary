# Gini Index
- The Gini index measures **class impurity** as $Gini(D)=1-\sum_{i=1}^mp(y=y_i)^2$
- If we split via attribute $A$ into partitions $\{D_1, D_2, . . . , D_v \}$, the Gini index of this partitioning is defined as $$Gini_A(D) = \sum_{j=1}^v\frac{|D_j|}{|D|}Gini(d_j)$$
- and the reduction in impurity by a split on $A$ is $$\Delta Gini(D)= Gini(D)-Gini_A(D)$$
