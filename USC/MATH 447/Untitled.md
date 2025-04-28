$$
X \rightarrow^\psi \rightarrow H (\text{vector space with an inner product, possibly infinite dimensional})
$$
### Example - Polynomial Regression
Finding $p(k)$ of degree $k$
Trying to come up with a polynomial such that $p(x_{i})\approx y_{i}$.
Finding the polynomial is the same as a linear combination of the features (1,x,x^2,...,x^k,y). So this becomes a linear problem on a higher dimensional space.

#### Main Idea
The mapping $\psi$ only manifests itself as dot products.$$
<\psi (x_{i}),\psi(x_{j})>
$$
is the only information we need.
Now, introduce kernel in $X$ is a function $K:X\times X\rightarrow R$ such that $$
K(\vec{X_{1}}, \vec{X_{2}}) = <\psi(\bar{X_{1}}), \psi(\bar{X_{2}})> 
$$Where the kernel is a measure of similarity

#### Example = 