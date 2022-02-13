# Graph-based clustering
## Dataset
- dataset $D$ is given in terms of a graph $G=(V,E)$
- a *data object* $v_i$ is a node in $G$
- edge $e_{ij}$ from node $v_i$ to node $v_j$ has the weight $w_{ij}$

 ## Basic Graph based clustering Algorithm
 - define threshold $\theta$
 - remove all edges $e_{ij}$ with weight $w_{ij} > \theta$ 
 - **Each connected component** of the graph now corresponds to **one cluster**. 

## Moreover
 - Two nodes are in the same connected component if there is a path between them. 
 - Graph components can be found by depth-first search in a graph $(O(|V| + |E|))$
 - The graph can be made with existing data such as: telecommunciation or soial networks
 - Or we can create it by using a [[Distance Functions]] d by 
 - connecting each node by it's K-nearest neighbour with [[Nearest Neighbour Classification]]
 - or simply connecting each node with their $\epsilon$ neighbourhood

## More advanced Graph based clustering Algorithm
## [[DBscan]]
