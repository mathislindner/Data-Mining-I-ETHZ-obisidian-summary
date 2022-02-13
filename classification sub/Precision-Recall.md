# Precision-Recall
If the positive class is much smaller than the negative class we should use 
- precision $$\frac{TP}{TP+FP}$$
- recall $$\frac{TP}{TP+FN}$$
## Trade-Off between Precision and Recall
- By Predicting all points to be positive $f(x=1)$ one can guarantee that the recall is 1. However the precision then will be bad.
- By only predicting points to be members of the positive class for which one is highly confident about the prediction, one will increase precision, but lower recall.
- One workaround is to report the precision recall break-even point, that is the value at which precision and recall are identical.

## Example of Recall 

![[Pasted image 20220212213700.png]]

