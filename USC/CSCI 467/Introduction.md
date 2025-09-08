8/25/25
Machine learning is defined as learning from experience (data) to detect patterns and show results
y

8/27/25

23/41
Decision tree with discreet features
- After taking in training data, leaves are analogous to labels - outcomes.
- Each internal node is a particular feature
With continuous features
- Define thresholds/ranges and define into buckets - hyperparameters

Every time you run an NP hard problem, you take a greedy approach because it always terminates - will most likely be suboptimal 
Training is expensive, but predictions are cheap since its a tree, vice versa for KNN

34/41
As you traverse and build the tree, number of features decreases and eventually will terminate

9/3/25
Gini Impurity implemented to reduce cost of entropy and calculating logs, called CART.