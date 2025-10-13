### Theorem 3.10
#### Proof
a) To prove diam$E$ = diam$\bar{E}$, prove 
1. diam$E\leq$diam$\bar{E}$
    1. Since $E \subset  \bar{E}$ we get this immediately
2. diam$E\geq$ diam$\bar{E}$
    1. Fix $\epsilon>0,$ choose $p,q \in  \bar{E}$. Then we know $\exists p',q' \in E$ such that $$
d(p,p') < \frac{\epsilon}{2}, d(q,q') < \frac{\epsilon}{2}
$$
Thus
$$
d(p,q) \leq d(p,p') + d(p',q)
$$
$$
\leq d(p,p') + d(p',q') + d(q',q)
$$
$$
< \frac{\epsilon}{2} + \frac{\epsilon}{2} + d(p',q') = \epsilon + d(p',q')
$$
$$
\text{diam}(\bar{E}) \leq \epsilon + \text{diam}(E)
$$
Since $\epsilon>0$ was arbitrary, we have 2. So 1 and 2 imply diam$(\bar{E})=$diam($E$)
b) Let $K= \cap^\infty K_{n }$ each $K_{n}$ is compact and $K_{n} \supset K_{n+1}$ for each $n$.
Theorem 2.36 Tells $K$ is not empty. It remains to show that $K$ is a single point. We know $$
\lim_{n\to \infty} \text{diam}K_{n}=0 \quad (3)
$$
If $K$ has more than one point. lets say $x,y$ such that $x\neq y$ then $d(x,y)>0$ so diam$K>0$. Suppose diam$K=\delta$. Since (3) is true, $\exists N$ such that diam$K_{n}<\delta$, contradicting the assumption (3). Thus $K$ must be a single point.

### Theorem 3.11
How do Cauchy sequences and convergent sequences relate?
a) In any metric $(X,d)$, every convergent sequence is Cauchy.
    converges of $\{p_{n}\} \implies \{p_{n}\}$ is Cauchy
b) If $X$ is compact, $\{p_{n}\}$ is Cauchy in $X$ $\{p_{n}\}$ converges to $p$ in $X$
c) In $\mathbb{R}^k$, every Cauchy sequence converges.
##### Remark
3.11c is known as the Cauchy  for sequences in $\mathbb{R}^k$.
- Theorem is useful because we can talk abut convergent sequences without knowing to were they are convergent.
#### Proof
a) If $p_{n} \to p$ in $(X,d)$ and $\epsilon > 0,$ $\exists N$ such that $d(p,p_{n}) < \frac{\epsilon}{2}$ for $n \geq N$. Thus 
$$
d(p_{n}, p_{m}) \leq d(p_{n},p) + d(p,p_{m}) < \frac{\epsilon}{2} + \frac{\epsilon}{2}
$$
$\implies d(p_{n},p_{m}) < \epsilon$, so $\{p_{n}\}$ is Cauchy if it converges
b) In compact $X$, $\{p_{n}\}$ Cauchy $\implies$ it converges to a point in $X$.
Let $\{p_{n}\}$ be Cauchy in $(X,d)$, where $X$ is compact. For each $N=1,2,\dots,$ let $E_{n} = \{p_{N},p_{N+1},\dots \}$ we know 
$$
\lim_{n \to \infty} \text{diam} \bar{E}_{n}=0 \quad (1)
$$
by definition of Cauchy sequence and theorem 3.10a
- Each $\bar{E}_{n}$ is closed
- Therefore, each $\bar{E}_{n}$ is compact (closed subsets of compact sets are compact, $X$ is compact)
- Finally, $E_{n} \supset E_{n+1}$, so $\bar{E}_{n} \supset \bar{E}_{n+1}$.
Combine all of this and apply theorem 3.10b to state that there is a unique point $p$ in $X$ such that $p \in E_{n}$ for all $N$.

Let $\epsilon > 0$ be given. By (1), $\exists N_{0}$ such that diam$\bar{E}_{n} < \epsilon$ for $N \geq N_{0}$. Since $p \in \bar{E}_{n}$, $d(p,q) <\epsilon$ for any $q \in \bar{E}_{n}$, thus for each $q \in E_{n}$, and since $q=p_{n}$ for some $n \geq N$, we know $p_{n}\to p$

c) Let $\{\vec{x}_{n}\}$ be Cauchy in $\mathbb{R}^k$. Let $E_{n}$ be defined as it was in b):
$$
E_{n}= \{ \vec{x_{n}}, \vec{x}_{n+1},\dots\}
$$
For some $N$, diam$E_{n}<1$
. The range of $\{\vec{x}_{n}\}$ is then the union of $E_{n}$ and the finite set $\{\vec{x}_{1},\vec{x}_{2},\dots,\vec{x}_{N-1}\}$, hence the range of our sequence is bounded. Every bounded subset of $\mathbb{R}^k$ has compact closure (Theorem 2.41), so c) follows by applying b) if we fix a k-cell $I$ which contains our range.

#### Definition 3.12
A space $(X,d)$ where all Cauchy sequences converge is called a complete metric space.
#### Remark:
- Theorem 3.11 says compact metric spaces and Euclidian spaces are complete.
- Every closed subset of a complete metric space is also complete
- $(\mathbb{Q},d)$ with $d(x,y) = |x-y|$ is an example of a metric space which is not complete