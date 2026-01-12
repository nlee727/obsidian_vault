#### Theorem 1.35 - Cauchy-Schwarz inequality
If $a_{1},\dots ,a_{n}$ $b_{1},\dots,b_{n}$ are complex numbers, then $$
\left | \sum_{{j=1}}^n a_{j} \bar{b}_{j} \right |^2 \leq \sum_{j=1}^n |a_{j}|^2 - \sum_{j=1}^n |b_{j}|^2
$$
#### Remarks
- This works for $a_{j}'s$ and $b_{j}'s$ being real numbers
- If a and b are vectors,
$$
(\vec{a}^T \vec{b})^2 = <\vec{a},\vec{b}>
$$
#### Proof
$$
\left | \sum_{{j=1}}^n a_{j} \bar{b}_{j} \right |^2 \leq \sum_{j=1}^n |a_{j}|^2 - \sum_{j=1}^n |b_{j}|^2
$$
Let
$$
A =  \sum_{j=1}^n |a_{j}|^2
$$
$$
B = \sum_{j=1}^n |b_{j}|^2
$$
$$
C = \sum_{j=1}^n a_{j}\bar{b_{j}}
$$
If $B=0$ then $b_{j}=0$ for each $j$ and the conclusion is immediate, so assume $B\neq 0$
By Theorem 1.31 (conjugates behave well with sums and products), we see
$$
\sum |Ba_{j}-Cb_{j}|^2 = \sum (Ba_{j} - Cb_{j}) (B \bar{a_{j}}- \bar{C_{b_{j}}})
$$
##### Note
$$
\bar{ZW} = \bar{Z} \bar{W} \quad (Z \bar{Z})^\left( \frac{1}{2} \right) = |Z|
$$
so,
$$
= B^2 \sum |a_{j}|^2 - B \bar{C} \sum a_{j}\bar{b_{j} } - BC\sum \bar{a_{j}} b_{j} + |C|^2\sum|b_{j}|^2
$$
$$
=B^2A - |C|^2B + 0
$$
$$
= B(AB - |C|^2) \geq 0
$$
Since $B> 0$ $$
\implies \mid C\mid^2 \leq AB \text{, exactly the inequality}
$$
## Show $R^k$ is separable
#### Definition
A metric space (X,d) is separable if it has a countable dense subset

A set $Y \subseteq X$ is dense in X if every pt of X is either a limit pt of Y or is a point of Y

Want to show $R^k$ has a countable dense subset

Candidate: $\mathbb{Q^k}$
- $\mathbb{Q^k}$ is countable because it is in 1-1 correspondence with $k$ copies of $\mathbb{Q}$, which are countable
- Must argue $\mathbb{Q^k}$ is dense in $\mathbb{R^k}$.
To show that $\mathbb{Q}$ was dense in $\mathbb{R}$, we showed that in any open interval (a,b), there exists some rational number $q$ such that $a <q<b$. Which is sufficient to argue that every nonempty open set of $\mathbb{R^k}$ has a point with rational coordinates.

Let $E$ be a nonempty open subset of $\mathbb{R}^k$. Since $E$ is nonempty, pick $\vec{x_{0}} \in E$. $E$ open $\implies \vec{x_{0}}$ is an interior point, meaning that $\exists r>0$ such that for points $\vec{y} \in \mathbb{R}^k$ satisfying $|\vec{x_{0}}-\vec{y}| < r$ says that $\vec{y \in E}$.

In particular, let $\vec{x_{o}}=(x_{01},x_{02},\dots, x_{0k})$, then for the j-th entry, we see tha tin the j-th coordinate, any point $\vec{y}=(\dots,y_{j},\dots)$ has 
$$
x_{0j}-r < y_{j}< x_{0j} + r \implies
$$
can find a rational $q_{j}$ such that $$
x_{0j}-r < q_{}{j}< x_{0j} + r \implies
$$
do this for each entry to obtain
$$
\vec{q}= (q_{1},q_{2},\dots,q_{k})
$$ which belongs to $E$ because 
$$
|\vec{X_{0}}
$$