# Classification Threshold

$$
f(x) = 1 \space if \space s(x) \geq \theta
$$
$$
f(x) = -1 \space if \space s(x) < \theta
$$
$s: D \rightarrow \mathbb{R}$ is a **scoring function** and $\theta$ is a **threshold** 

#TODO

## How to report results as a function
- The efficient strategy to compute all solutions as a function of $\theta$ is to rank all points x by their score s(x). This ranking is a vector of length t. 
- This ranking is a vector r of length t, whose ith element is r(i). We then perform the following steps: For i = 1 to t − 1 
	- Define the positive predictions P to be the set {r(1), . . . ,r(i)}. 
	- Define the negative predictions N to be the set {r(i + 1), . . . ,r(t)}. 
	- Compute the evaluation criteria e(i) of interest for P and N. 
	- Return vector e 
- The common strategy is to compute two evaluation criteria e1 and e2 and to then visualize the result in a 2-D plot.

## Receiver Operating Characteristics Curve (ROC)
[Video](https://www.youtube.com/watch?v=4jRBRDbJemM)
![[Pasted image 20220212213347.png]]
![[Pasted image 20220212213410.png]]
##  Area under the Receiver Operating Characteristics (AUC)
- The solution to this problem is the Area under the Receiver Operating Characteristics (AUC), a number between 0 and 1. 
- The AUC can be interpreted as follows: When we present one negative and one positive test point to the classifier, then the AUC is the probability with which the classifier will assign a larger score to the positive than to the negative point. 
- The larger AUC, the better the classifier. 
- The AUC of a perfect classifier can be shown to be 1. 
- The AUC of a random classifier (guessing the prediction) is 0.5. 
- The AUC of a ‘stupid’ classifier (misclassifying all points) is 0.