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

#### Gaussian Kernel
$$
K(\vec{x},\vec{x}')=e^{-||\vec{x}-\vec{x}'||^2/2\sigma}
$$
##### Problem
$$
\min f(<w,\psi(x_{1})>, <w,\psi(x_{2})>\dots<w,\psi(x_{m})+R(||w||)), \text{ R is non decreasing on }[0,\infty)
$$
Soft SVM $R(a)=\lambda a^2$
$$
f(a_{1},a_{2},\dots,a_{m})=\frac{1}{m}\sum \max\{0,1-y_{i},a_{i}\}
$$
Hard SVM $R()=()^2$
$$
f(a_{1},a_{2},\dots,a_{m})=0, \exists b:y_{i}<a_{i}+b> \geq 1 \forall i ,\infty \text{ otherwise}
$$
Penalize with infinity so that it cannot be minimized

Thm (Representer Thm) There is a solution to $\min f(<w,\psi(x_{1})>, <w,\psi(x_{2})>\dots<w,\psi(x_{m})+R(||w||)), \text{ R is non decreasing on }[0,\infty)$ in the form 
$$
(!) \cdot w = \sum_{i=1}^m \alpha_{i}\psi(\bar{x}_{i})
$$
Linear combination of Hilbert space
Hilbert Space 
H - vector space with an inner product

The structure of F(w) is such that you can always find a solution in the previous form.

The problem is equivalent to 
$$
\min_{\alpha}f\left( \sum_{i=1}^m \alpha_{i} < \psi(\bar{x_{i}}),\psi(\bar{x_{1}})>,\sum_{i=1}^m \alpha_{i} < \psi(\bar{x_{i}}),\psi(\bar{x_{2}})>,\dots\right)+R\left( \sqrt{ \sum \alpha_{i}\alpha_{j}<\psi(\bar{x_{i}}) ,\psi(\bar{x_{j}})>} \right)
$$
$$
 < \psi(\bar{x_{i}}),\psi(\bar{x_{1}})> = K(\bar{x_{i}},\bar{x_{1}})
$$
$$
 < \psi(\bar{x_{i}}),\psi(\bar{x_{j}})> = K(\bar{x_{i}},\bar{x_{j}})
$$
We don't know what the mapping $\psi$ is, we only need the dot product given by the kernel. The kernel is fixed and implicitly defines a mapping and feature space.

## 5/2/25
Given $K: X \times X\to R$
When is K a kernel?
When is there a F (Hilbert Space) and a mapping $X \to \mathcal{F}$ such that $K(x,y) = <\psi(x),\psi(y)>_{\mathcal{F}}$

Thm: K is a valid kernel $\iff$ it is symmetric $K(x,y)=K(y,x)$, and PSD $\forall\{x_{1},\dots,x_{m} \}$, the matrix $G_{ij}=K(x_{i},x_{j})$ is positive semi-definite ($G_{ij}\alpha^i\alpha^j \geq 0 \quad \forall \vec{\alpha}$)
Proof:
Start with $R^X=\{f:X\to R\}$
Given $x \in X, \psi(x)(\xi)=K(\xi ,x)$
$\mathcal{F}=\text{span of }\{K(\xi ,x)\}$ is a vector space
We have to define the inner product structure
Take two linear combinations of F
$$
<\sum\alpha_{i}K(\xi ,x_{i}),\sum\beta_{j}K(\xi,x_{j})>_{F}
$$
Check
1) $K(X,X')= <\psi(x),\psi (x')>_{F}$
2) $<\quad , \quad>_{F}$ is indeed an inner product

You know there is some $\psi$ and some $F$. However if you know the kernel, thats all you need to implement SVM with kernels
#### SGD for Soft SVM with kernels
##### No kernels
$\theta^{(1)}=\vec{0}$
For $t=1,\dots T$
1) $w^{(t)}=\frac{1}{\lambda t}\theta^{(t)}$
Choose $i \sim Uniform[m]$
    If $y_{i}<w^{(t)},x_{i}> < 1$
        $\theta^{(t+1)}=\theta^{(t)}+y_{i}x_{i}$
    Else:
        $\theta^{(t+1)}=\theta^{(t)}$
Output $\vec{w}=\frac{1}{T}\sum_{t=1}^T w^{(t)}$

##### Using kernels:
$x_{i}\to \psi(x_{i})$
$\theta$ was a linear combination of $x_{i}$. 
$$
\theta^{(t)}=\sum_{j=1}^m \beta_{j}^{(t)}\psi(x_{j})
$$
W is proportional to $\theta$, so it is also a linear combination
$$
w^{(t)}=\sum \alpha_{j}^{(t)}\psi(x_{j})
$$
1) $\alpha^{(t)}=\frac{1}{\lambda t} \beta^{(t)}$
Choose $i \sim Uniform[m]$
If $y_{i} \sum\alpha_{i}^{(t)} K(\vec{x_{j}}, \vec{x_{i}})<1$
    $\beta^{(t+1)}_{i}=\beta_{i}^{(t)}+y_{i}, \quad \beta_{j}^{(t+1)}=\beta_{j}^{(t)},j \neq i$ (we don't need $x_{i}$ because we are not looking at $\theta$ itself) 
Else:
    $\beta^{(t+1)}=\beta^{(t)}$
Output: $\bar{\alpha}=\frac{1}{T}\sum_{t=1}^T\alpha^{(t)}$
    $\bar{w}=\sum \bar{\alpha}_{j}\psi(x_{j)}$ (this would be the w but you dont need this, you only need the dot product to make predictions)
Prediction:
    For $\vec{x} \in X:$
    $$
<\bar{w}, \psi(x) > = <\sum \bar{\alpha}_{j}\psi(\bar{x}_{j}), \psi(x)> = 
$$
$$
\sum \bar{\alpha_{j}} <\psi(\bar{x}_{j}),\psi(x)=
$$
$$
\sum \bar{\alpha}_{j}K(\bar{x_{j}},\bar{x})
$$
You don't care about w, you care about the dot product/prediction (positive or negative)
