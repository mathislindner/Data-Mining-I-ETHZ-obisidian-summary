# Greedy Selection
- Greedy selection is an alternative to **exhaustive enumeration**
-  Idea is to iteratively 
	- add the currently most informative feature to the selected set or 
	- remove the currently most uninformative feature from the solution set 
- These two variants of greedy feature selection are referred to as: **forward feature selection backward elimination**
## Optimality
- Only optimal if q **decomposes** over the elements of S
$$q(S) = \sum_{c \in S} q(x)$$
- Near-optimal if q is  a **[[Submodular Functions]]** 
- Otherwise there is **no guarantee for optimality**.
## Algorithms
### Forward feature Selection
![[Pasted image 20220214131058.png]]
### Backward feature Elimination
![[Pasted image 20220214131124.png]]