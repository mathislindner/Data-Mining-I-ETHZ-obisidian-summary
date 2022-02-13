# Decision Tree
## Definition
[video](https://youtu.be/7VeUPuFGJHk)
- Recursively split the data space into regions that contain a single class only
![[Pasted image 20220213132413.png]]
- a root: this is the uppermost node 
- internal nodes: these represents tests on an attribute 
- branches: these represent outcomes of a test 
- leaf nodes: these hold a class label

## Popularity
- requires no domain knowledge 
- easy to interpret 
- construction and prediction is fast 

## Advantages
- Simple to understand and to interpret. Trees can be **visualised**. 
- Requires **little data preparation**. Other techniques often require data normalisation, dummy variables need to be created and blank values to be removed. 
- The cost of using the tree (i.e., **predicting data**) is **logarithmic** in the number of data points used to train the tree. 
- Able to handle both** numerical and categorical data**. Other techniques are usually specialised in analysing datasets that have only one type of variable. See algorithms for more information. 
- Able to handle **multi-output problems**. 
- Uses a **white box model**. If a given situation is observable in a model, the explanation for the condition is easily explained by boolean logic. By contrast, in a black box model (e.g., in an artificial neural network), results may be more difficult to interpret.
- Possible to **validate** a model using statistical tests. That makes it possible to account for the **reliability** of the model. 
- **Performs well** even if its assumptions are somewhat violated by the true model from which the data were generated.
## Disadvantages
- Decision-tree learners can **create over-complex trees** that do not generalise the data well. This is called overfitting. Mechanisms such as **pruning**, setting the minimum number of samples required at a leaf node or setting the **maximum depth** of the tree are necessary to avoid this problem. 
- Decision trees can be **unstable** because small variations in the data might result in a completely different tree being generated. This problem is mitigated by using decision trees within an ensemble. 
- The problem of learning an optimal decision tree is known to be **NP-complete** under several aspects of optimality and even for simple concepts. Consequently, practical decision-tree learning algorithms are based on **heuristic algorithms** such as the greedy algorithm where locally optimal decisions are made at each node. Such algorithms cannot guarantee to return the globally optimal decision tree. This can be mitigated by training multiple trees in an **ensemble learner**, where the features and samples are randomly sampled with replacement.
- There are concepts that are **hard to learn** because decision trees do not express them easily, such as XOR, parity or multiplexer problems.
- Decision tree learners create **biased trees** if some classes dominate. It is therefore recommended to **balance the dataset** prior to fitting with the decision tree.

## Classification 
- given a test point $x$ 
- perform test on the attributes of x at the root 
- follow the branch that corresponds to the outcome of this test 
- repeat this procedure, until you reach a leaf node 
- predict the label of x to be the label of that leaf node

## Construction of the Tree
1) Start with all training examples
2) Select attribute and threshhold that gives the **Best** Split
3) Create child nodes based on split
4) Repeat Step 2 and 3 on each child using its data until a **stopping criterion** is reached
	- all examples are in the same class 
	- number of examples in a node is too small 
	- the tree gets too large

## Details on tree construction
- If Stopping Criterion fulfilled: Predicted class for points in $D$ is the majority class in $D_i$ 
- Otherwise
	-  $arg max(A,θ) = cost(D) − cost(DA,θ)$
	- $D_A,<θ = \{x ∈ D|A < θ\}$
	- $D_A,≥θ = \{x ∈ D|A ≥ θ\}$
	- Create two child nodes of D, containing DA,<θ and DA,≥θ 
	- DecisionTree $(D_A,<θ)$
	- DecisionTree $(D_A,≥θ)$
- end

## Split gain
There are different ways to choose our splits, one way is with  [[Information Gain]]
Another one is using the [[Gini Index]]

## Further investigation
- To **minimize overfitting** and the large variability in decision trees, one may use **an ensemble** of several decision trees.
-  Breiman (2001) introduced [Random Forests](https://youtu.be/J4Wdy0Wc_xQ) a collection of k decision trees. The idea is to subsample a subset of n' instances and a subset of d' features of the training dataset k times. 
	- On each of these k samples, a decision tree is constructed. 
	- Subsequently, the classification of trees is performed by taking a majority vote over the trees. 
	- Three key parameters: number of instances in the subset n' , number of features in the subsets d' , and number of trees k.