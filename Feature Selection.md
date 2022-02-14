# Feature Selection
- Usually, our output variable Y does not depend on all of our input features X. 
- In fact, we perform **supervised learning** to determine this **dependence** between input variables and output variables. ( #Supervised ) feature selection means selecting the relevant subset of features for a **particular learning task**. 
- Note the difference to **feature ranking**, which orders features according to their relevance, and f**eature transformation**, which translates the original features into a **new feature representation**

## Why feature selection
- to detect causal features
- to remove noisy features
- to reduce the set of features to be observed
- to reduce cost and to improve speed and data understanding

## Two Approaches

### [[Filter Approaches]]
Select interesting features **a priori**, based on a **quality function**(information criterion)

### [[Wrapper Approaches]]
Select special features that are interesting for one particular classifier

## In Practice
Catalog by Guyon and Eliseeff
1. Do you have domain knowledge? If yes, construct a better set of ad-hoc features.
2. Are your features commensurate? If no, consider normalizing them. 
3. Do you suspect interdependence of features? If yes, expand your feature set by constructing conjunctive features or products of features, as much as your computer resources allow you. 
4. Do you need to prune the input variables (e.g. for cost, speed or data understanding reasons)? If no, construct disjunctive features or weighted sums of features.
5. Do you need to assess features individually (e.g. to understand their influence on the system or because their number is so large that you need to do a first filtering)? If yes, use a variable ranking method; else, do it anyway to get baseline results. 
6. Do you need a predictor? If no, stop. 
7. Do you suspect your data is “dirty” (has a few meaningless input patterns and/or noisy outputs or wrong class labels)? If yes, detect the outlier examples using the top ranking variables obtained in step 5 as representation; check and/or discard them.
8. Do you know what to try first? If no, use a linear predictor. Use a forward selection method with the “probe” method as a stopping criterion or use the $\ell_0$-norm. embedded method. For comparison, following the ranking of step 5, construct a sequence of predictors of same nature using increasing subsets of features. Can you match or improve performance with a smaller subset? If yes, try a non-linear predictor with that subset. 
9. Do you have new ideas, time, computational resources, and enough examples? If yes, compare several feature selection methods, including your new idea, correlation coefficients, backward selection and embedded methods. Use linear and non-linear predictors. Select the best approach with model selection.
10. Do you want a stable solution (to improve performance and/or understanding)? If yes, subsample your data and redo your analysis for several “bootstraps”.

## Moreover
- Can presumably redundant variables help each other? 
	->Noise reduction and consequently better class separation may be obtained by adding variables that are presumably redundant. 	
- How does correlation impact variable redundancy? 
	->Perfectly correlated variables are truly redundant in the sense that no additional information is gained by adding them. 
	->Very high variable (anti-)correlation does not mean absence of variable complementarity. 
- Can a variable that is useless by itself be useful with others? 
	->Two variables that are useless by themselves can be useful together