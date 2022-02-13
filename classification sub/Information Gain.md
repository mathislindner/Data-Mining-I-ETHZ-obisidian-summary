# Information  Gain
## Shannon entropy of D
$$Info(D)=-\sum_{i=1}^mp(y=y_i|x\in D)\log_2(p(y=y_i|x\in D))$$
$p(y=y_i|x \in D)$ being the probability that an arbitrary tuple in $D$ belongs to class $y_i$  and is estimated by $$\frac{|(x_j,y_j)|x_j\in D \cap y_j=y_i}{|D|}$$

- Assume that attribute A was used to split $D$ into v partitions or subsets, $\{D_1, D_2, . . . , D_v \}$, where $D_j$ contains those tuples in $D$ that have outcome $a_j$ of A. 
- Ideally, the $D_j$ would provide a perfect classification, but they seldomly do. 
- How much more information do we need to arrive at an exact classification?
$$Info_A(D)= \sum_{j=1}^{v}\frac{|D_j|}{D}Info(D_j)$$
## Information Gain
Pick $A$ such that the gain is **maximised**
$$Gain(A) = Info(D)-Info_A(D)$$
### Gain ratio
- The information gain is biased towards attributes with a **large number of values **
- For example, an ID attribute maximises the information gain! 
- Hence C4.5 uses an extension of information gain: the gain ratio 
- The gain ratio is based on the split information
$$SplitInfo_A(D)=-\sum_{j=1}^v\frac{|D_j|}{|D|}\log_2(\frac{|D_j|}{|D|})$$
$$GainRatio(A)= \frac{Gain(A)}{SplitInfo_A(D)}$$
- The attribute with maximum gain ratio is selected as the **splitting attribute** 
- The ratio becomes **unstable**, as the **split information** approaches **zero** 
- A constraint is added to ensure that the information gain of the test selected is **at least as great** as the average gain over all tests examined.
