# Submodular functions
## Definition
a function q on a set D is said to be submodular if
$$s(S\cup X)-q(S)\geq q(T\cup X)-q(T)$$
- $X \in D$
- $S \subset D$
- $T \subset D$
- $S \subseteq T$

- This is referred to as the property of ‘diminishing returns’: 
	- If S is a subset of T, 
	- then S **benefits more** from adding **X than T**

## Near optimality
- If q is a submodular, nondecreasing set function and $q(∅) = 0$, then the greedy algorithm is guaranteed to find a set S such that
$$q(S)\geq(1-\frac{1}{e})max_{|T|=|S|}q(T)$$
This means that the solution of greedy selection reaches **at least** ∼ 63% of the quality of the **optimal solution**

## Sensor Placement
- Imagine our features form a graph $G = (D, E)$ 
- Imagine the features are possible locations for a sensor. Each sensor may cover a node v and its neighbourhood $\mathcal{N} (v)$ (including node v), that is $q(S) = |\cup_v  \mathcal{N} (v)|$. 
- Now we want to pick locations in the graph such that our sensors cover as large an area of the graph as possible. 
- q fulfills the following properties 
	- $q(∅) = 0$ q is non-decreasing 
	- q is submodular 
- Hence greedy selection will lead to near-optimal sensor placement
