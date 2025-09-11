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

9/8/25
## Boosting
Sequence of machine learning algorithms in such a way that one helps the next. 
- Don't need on a neural network, more on weak algorithms to boost accuracy

### Problem 2
$$
h_{1}=sign(x-3.5)
$$
$$
D_{1}=\frac{1}{8}
$$
$$
\epsilon_{1}=\frac{1}{8},\beta_{1}=\frac{1}{2}\ln\left( \frac{1-\epsilon_{1}}{\epsilon_{1}} \right)=\frac{1}{2}\ln(7)
$$
recalculate weights
$$
D_{2}^{\text{err}}=D_{1} \cdot \exp(\beta_{1})=\frac{1}{8}\sqrt{ 7 }
$$
$$
D_{2}^{\text{cor}}=D_{1} \cdot \exp(-\beta_{1}) = \frac{1}{8}\frac{{ 1 }}{\sqrt{ 7 }}
$$
normalization
now point 8 has weight $\frac{1}{2}$ and everything else has weight $\frac{1}{14}$
$$
D_{2}=
$$
How do you pass knowledge from one classifier to the next? The training weight so that the next classifier will try to classify the harder points.


Sep 10
16/34
Adaboost requires a pool of classifiers, if its less than 50% it will pose a huge problem

T (Look at slide 4 and beta)
F (Less than 50% accuracy and beta will be negative so things will be flipped)
F ()
F (Always going to go weight 1/2)
F ()
