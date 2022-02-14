# Optimisation Problem
- Given a set of features D, 
- A quality function q
- we try to find the subset S of D of cardinality n' that maximises q
$$argmax_{s\subset D\wedge|S|=n'}q(S)$$
## Runtime
- The computational effort for enumerating all possibilities is exponential in n 0 , and hence intractable for large D and n 0 . 
- In practice, we have to find a workaround!