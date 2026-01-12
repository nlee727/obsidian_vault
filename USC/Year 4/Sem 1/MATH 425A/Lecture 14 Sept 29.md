Tools we need:
### Theorem 2.35
Closed subsets of compact sets are compact
### Theorem 2.37
If E is an infinite subset of a compact set K, then E has a limit point in K.
### Theorem 2.39
Let k be a positive integer. If $\{I_n\}$ is a sequence of k-cells with the property $I_{n+1} \subset I_{n}$ then $\cap_{n=1}^{\infty} I_{n}$ is nonempty
### Theorem 2.40
Every k-cell is compact
#### Proof:
Let $I=\{\vec{x} \in \mathbb{R}^k|\vec{x}=(x_{1},x_{2},\dots,x_{k})$ wit $a_{j}\leq x \leq b_{j}$ for $i=1,2,\dots,k$
Let $\delta = \left[ \sum_{i=1}^k (b_{i} - a_{i})^2 \right]^{\frac{1}{2}}$
For any $\vec{x},\vec{y} \in I,$ $|\vec{x} - \vec{y}| \leq \delta$
Suppose for a contradiction that $\exists \{G_{\alpha}\}$ an open cover that admits no finite subcover (no compactness) of $I$.

For each $i$, $c_{i }=\frac{b_{i}-a_{i}}{2}$ i.e., $c_{i}$ is the midpoint of $[a_{i},b_{i}]$ for each $i$.
This given us several smaller new k-cells. At least one of these smaller k-cells must not have a finite subcovering. Call this specific k-cell $I_{1}$. Repeat this process to get a sequence of k-cells $\{I_{n}\}$ such that 
$$
I \supset I_{1} \supset I_{2} \supset \dots
$$
$$
\text{ Each }I,I_{n} \text{ for }n=1,2,\dots \text{ is not covered by any finite subcollection of } \{G_{\alpha}\}
$$
$$
\text{If }\vec{x},\vec{y} \in I_{n}, \text{ then }|\vec{x}-\vec{y}| \leq \frac{\delta}{2^n}
$$
### Theorem 2.39
Tells us that $\exists \vec{x^*}$ that exists in every $I_{n}$.

Then, $\exists \alpha$ such that $\vec{x}^* \in G_{\alpha}$. $G_{\alpha}$ is open $\to \exists r>0$ such that $|\vec{y}-\vec{x^*}| < r$ implies $y \in G_\alpha$. If $n$ is large enough, such that $\frac{\delta}{2^n} < r$ (we can always find such an n), then c) tells us $I_{n}\subset G_{\alpha} \to$ n-th k-cell $I_{n}$ is small enough to live in $G_{\alpha}$. This contradicts b), because $I_{n}$ is covered by $G_{\alpha}$. So we are done.

### Theorem 2.41
If $E \in \mathbb{R}^k$ satisfies one of the following, then it satisfies all three
1. $E$ is closed and bounded
2. $E$ is compact
3. Every infinite subset of $E$ has a limit point in $E$.
#### Proof
Show $1 \implies 2, 2 \implies 3, 3 \implies 1$
If 1 is true then $E \subset I$ for some k-cell $I$ and then 2 follows from theorem 2.40 and 2.35
If 2 is true $E$ is compact, then theorem 2.37 says that 3 directly follows

First we show $E$ not bounded $\to$ not every infinite subset of $E$ has a limit point in $E$.
$$
\neg 1 \implies \neg 3
$$
If $E$ is not bounded, $E$ contains points $x_{n}$ such that $|x_{n}| > n$ (positive integers)
Let $S$ be the set of these points $x_{n}$. 
Then, $S$ must be infinite and have no limit point in $\mathbb{R}^k$ thus no limit point in $E$.
This is equivalent to showing "all infinite subsets have limits" $\to$ "is bounded" (contrapositive)

It remains to show that assuming 3, $E$ is closed. Assume 3 holds,
If $E$ is not closed, $\exists \vec{x}^0 \in \mathbb{R}^k$ such that $\vec{x}^0$ is a limit point of $E$ but not a member of $E$. Thus, there are points $\vec{x}_{n}$ such that $\vec{x}_{n} \in E$ and 
$$
|\vec{x}_{0} - \vec{x}_{n}| < \frac{1}{n}, \quad n=1,2,3,\dots
$$
(can use any decreasing sequence, this is just a nice one). $x_{0}$ is a limit point of $E$ meaning we can find $x_{n}'s$ 

Let $S$ be the set of these $\vec{x}^n$'s. $S$ is then infinite, $\vec{x}_{0}$ is its limit point, and it has no other limit point. Let $\vec{y} \in \mathbb{R^k}$. If $\vec{y} \neq \vec{x}$, then 
$$
|\vec{x}^n - \vec{y}| = |\vec{x}^n - \vec{x}^0 + \vec{x}^0 - \vec{y}| \geq |\vec{x}^0 - \vec{y}| -|\vec{x}^n - \vec{x}^0| > |\vec{x}^0 - \vec{y}| - \frac{1}{n}
$$
If we pick $\vec{x}_{n}$ close enough to $\vec{x}_{0}$, then 
$$
> |\vec{x}_{0}-\vec{y}| - \frac{1}{2}|\vec{x}_{0} - \vec{y}| = \frac{1}{2}|\vec{x}_{0} - \vec{y}|

$$
For all finitely many (ie the first group of ) $x_{n}$ ie $\vec{y}$ is not a limit point of $S$. So $S$ has no limit point of $E$ contradicts the assumption that every subset of $E$ (like $S$) has a limit point. Therefore $E$ must be closed.

### Theorem 2.42 Weierstrauss
Every bounded infinite subset of $\mathbb{R}^k$ has a limit point in $\mathbb{R}^k$
#### Proof
Let $E$ be one of these sets. Since $E$ is bounded, $E \subset I$ for some k-cell $I \subset \mathbb{R}^k$. By theorem 2.40, $I$ is compact, so $E$ has a limit point in $I$ by theorem 2.37.