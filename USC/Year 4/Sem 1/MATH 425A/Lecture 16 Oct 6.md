##### Aside (usual norms)
$$
\mathbb{R}: |x-y|
$$
$$
\mathbb{R}^2: ||x-y||_{2}
$$
There is also an absolute value
$$
\text{L}_{1}: |\vec{x}-\vec{y}| = \sum_{i=1}^2 |x_{i}-y_{i}|
$$
The unit ball of the $L_{1}$ norm is a diamond (taxi cab metric) whereas the $L_{2}$ is a unit circle

### One part of Thm 3.3 left to prove
$\{S_{n}\}, \{T_{n}\}$ are complex sequences such that $$
\lim_{n\to \infty} S_{n}=s, \lim_{n\to \infty} T_{n}=t
$$
d) $\lim_{n\to \infty} \frac{1}{S_{n}}=\frac{1}{s}$
#### Proof
Choose $m$ such that $S_{m}$ is this close to s:
$$
(1) \quad|S_{m}-s| < \frac{1}{2}|s|,
$$
and for all $m\subseteq n$
Apply reverse triangle inequality to $(1)$ to get $\frac{1}{2}|s| < |S_{n}|$ for $n \geq m$.

Given $\epsilon > 0, \exists n>m$ such that $n \geq N$ implies $$
(2) \quad |S_{n}-s| < \frac{1}{2}|s|^2 \epsilon
$$
(introducing a new factor in $|s|\epsilon$)
We see from here that $n \geq N$ gives $$
|\frac{1}{S_{n}}-\frac{1}{s}| = | \frac{{s-S_{n}}}{S_{n}s}|
$$
from (2),
$$
< \frac{1}{2} \frac{|s|^2}{|S_{n}s|} \epsilon 
$$
$$
< \frac{2}{2} \frac{|s|^2}{|s|^2} \epsilon = \epsilon
$$

### Theorem 3.4
a) Suppose $\vec{x}_{n} \in \mathbb{R}^k$ $n=1,2,3,\dots$ for a sequence $\{\vec{x}_{n}\}$, and $$
\vec{x}_{n}=(\alpha_{1,n},\alpha_{2,n},\dots,\alpha_{k,n})
$$
Then $\vec{x}_{n}\to \vec{x}=(\alpha_{1},\alpha_{2},\dots,\alpha_{k})$
iff $$(2) \quad \lim_{n\to \infty}\alpha_{j,n} = \alpha_{j}$$ for $j=1,2,\dots,k$
b) Suppose $\{\vec{x}_{n}\}$, $\{\vec{y}_{n}\}$ are sequences in $\mathbb{R}^k$ and $\{\beta_{n}\}$ is a sequence of real numbers with $\vec{x}_{n}\to \vec{x}, \vec{y}_{n}\to y, \beta_{n} \to \beta$
Then,
$$
\lim_{n\to \infty} (\vec{x}_{n}+\vec{y}_{n}) = \vec{x}+ \vec{y}
$$
$$
\lim_{n\to \infty}(\vec{x}_{n}\cdot \vec{y}_{n}) = \vec{x}\cdot \vec{y}
$$
$$
\lim_{n\to \infty}\beta_{n}\vec{x}_{n}=\beta \vec{x}
$$
#### Proof
a) epsilon proofs
$\implies$
Suppose $\vec{x}_{n} \to \vec{x}$ in Euclidian space $\mathbb{R}^k$. For each $j=1,2,\dots,k$, we get the following inequalities immediately:
$$
|\alpha_{j,n}-\alpha_{j}| = \sqrt{ |\alpha_{j,n}-\alpha_{j}|^2 }
$$
$$
 \leq \sqrt{ \sum_{j=1}^k  |\alpha_{j,n}-\alpha_{j}|^2} = ||\vec{x}_{n} - \vec{x}||_{2}
$$
due to the $L_{2}$ norm in $\mathbb{R}^k$.
In particular, $\forall \epsilon>0, \exists N$ such that $n \geq N$ says $||\vec{x}_{n}- \vec{x}||_{2} < \epsilon$. Note $$
 |\alpha_{j,n}-\alpha_{j}| \leq ||\vec{x}_{n}- \vec{x}||_{2} < \epsilon
$$ for each $j$, therefore each entry $\{\alpha_{j,n}\}$ converges to $\alpha_{j}$
$\impliedby$ 
Suppose (2):
$$
\lim_{n\to \infty} \alpha_{j,n}=\alpha _{j}
$$
for each $j$ holds.

Now for each $\epsilon>0, \exists N$ such that $n \geq N$ implies $$
|\alpha_{j,n}-\alpha _{j}| < \frac{\epsilon}{\sqrt{ k }},  \quad (1 \leq j \leq k)
$$
Then, $N\subseteq n$ implies $$
||\vec{x}_{n}- \vec{x}||_{2}=  \sqrt{ \sum_{j=1}^k  |\alpha_{j,n}-\alpha_{j}|^2}
$$
$$
<  \sqrt{ \sum_{j=1}^k  \left(\frac{\epsilon}{\sqrt{ k }}\right )^2} = \epsilon
$$

