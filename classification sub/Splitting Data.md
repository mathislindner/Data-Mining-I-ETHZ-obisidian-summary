# Splitting Data
- It is essential to split the data into a #training_set and a #test_set
- Splitting the dataset into k subsetsand using one of them for testing and the rest for training is referred to as *k-fold #cross-validation* 
- if $k = n$ , cross validation is reffered to as *leave-one-out-validation*
- Randomly sampling subsets of the data for training and testing and averaging over the results is called #bootstrapping.

### 10-Fold cross-validation
![[Pasted image 20220212215309.png]]

- Most classifiers use parameters **c** that have to be set
- It is wrong to optimize these parameters by trying out different values and picking those that perform best on the test set. These parameters are #**overfit** on this particular test dataset, and may **not generalize** to other datasets.
- Instead, one needs an internal cross-validation on the training data to optimize **c**.
![[Pasted image 20220212215859.png]]
![[Pasted image 20220212215922.png]]
