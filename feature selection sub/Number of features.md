# Number of features
- Pick all features that are significantly correlated with the output variable. 
	- Problem 1: Multiple testing problem: Even some randomly generated features may show a significant correlation. 
	- Problem 2: Ignores interactions and correlations between features. 
- Use the probe method (Bi et al., 2003, Stoppiglia et al., 2003, Tusher et al., 2003): 
- Insert ‘fake’ features (= probes) into the set of features. 
- Fake features can be drawn randomly from a Gaussian distribution, or they can be created in a nonparametric manner by randomly shuffling existing features. 
- Stop feature selection when you select the first fake feature or when the proportion of fake features exceeds a certain threshold.