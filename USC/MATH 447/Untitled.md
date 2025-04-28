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

#### Example 
$$
X=R
$$
$$
K(x,x') = (1+x x')^2 \text{ is a kernel in R (Polynomial kernel of degree 2)}
$$
$$
(1+x x')^2=1+2x x' + x^2x'^2= <(1,\sqrt{ 2 }x, x^2), (1, \sqrt{ 2 }x', x'^2)>
$$
$$
\psi(x)=(1, \sqrt{ 2 }x, x^2)
$$
More generally, $X=R$
$$
K(x, x')=(1+x x')^k
$$ is a kernel

If $X=R^d$
$$
K(\bar{X_{1}},\bar{X_{2}})=(1+<\bar{X_1},\bar{X_{2}}>_{R^d})^k= <\psi(\bar{x_{1}}), \psi (\bar{x}_{2})>_{R^{(d+1)^k}}
$$
The important part is that the function mimics the dot product in a higher dimensional space. You do not need to include all the new features


$$
X=R
$$
$$
\psi:R \rightarrow R^\infty
$$
$$
\psi(x)=\left( \dots, \frac{1}{\sqrt{ n! }} e^{-x^2/2} x^n, \dots\right)
$$
$$
< \psi (x), \psi (x')> = e^{-\frac{|x-x'|^2}{2}}=k(x,x')
$$
Is a kernel (Gaussian Kernel, RBF)