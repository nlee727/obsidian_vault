\### Definition
#### Remarks
In a metric space (X,d) 
- A,B separated $\implies$ A,B are disjoint
- A,B disjoint does not imply A,B are separated
In $\mathbb{R}$ with $d = |\cdot|$ $[0,1]$ and $(1,2)$ are disjoint but not separated, as $(1,2) = [1,2]$ has nonempty intersection with $[0,1]$.
However $(0,1)$ and $(1,2)$ are separated

### Theorem 2.47
A subset $E$ of the real line $\mathbb{R}^1$ is connected if and only if it has the following property:
if $x,y \in E \subseteq \mathbb{R}$ and $\exists z$ s.t. $x < z < y$, then $z \in E$ 
#### Proof:
We have two statements $A,B$ 
$A: E \subseteq \mathbb{R}$ is connected
$B: E$ has property

## Chapter 3 Numerical Sequences and Series
### Definition
A sequence $\{X_{n}\}$ is an infinite (usually countable) list of objects.
Given a sequence of points $\{P_{n}\}$ in a metric space $(X,d)$, we say that $\{P_{n}\}$ converges if $\exists p \in X$ such that the following happens:
For every $\epsilon > 0, \exists$ an integer $N>0$ such that $n \geq N$ implies that $$
d(p_{n},p) < \epsilon
$$
...
...
#### Remark
To be more precise, its sometimes helpful to say "convergent in $X$" or "divergent in $Y$" rather convergent or divergent if there is ambiguity
##### Ex:
$\left\{ \frac{1}{n} \right\}, n=1,2,3,\dots = \frac{1}{1}, \frac{1}{2}, \frac{1}{3}, \dots$
this diverges in $(0,2)$ because $0 \notin (0,2)$ but it converges in $\mathbb{R}$.

### Definition
Given a sequence $\{p_{n}\}$, the set of points $s = \{p_{1},p_{2},\dots \}$ is known as the range of $\{p_{n}\}$ is bounded if $S$ is bounded

##### Consider the following examples in $\mathbb{C}$
a) If $s_{n}=\frac{1}{n}$, then $\lim_{n\to \infty} s_{n} = 0$, range is infinite, and $\{s_{n}\}$ is bounded.
b) If $s_{n}=n^2$, $\{s_{n}\}$ is unbounded, divergent, and it has infinite range,
c) If $s_{n}=1 + \frac{(-1)^n}{n}=\{0, \frac{3}{2}, \frac{2}{3}, \frac{5}{4}, \dots\}$ $\{s_{n}\}$ converges to 1, its bounded and has infinite range
d) If $s_{n}=i^n = \{i,-1,-i,1,i, \dots\}$, $\{s_{n}\}$ diverges its bounded, and it has finite range.
e) If $s_{n}=1 \forall n$. then $s_{n}\to_{1}$, its bounded, and has finite range

Some basic properties of sequences in metric spaces
### Theorem 3.2
Suppose $\{p_{n}\}$ is a sequence in a metric space $(X,d)$.
a) $\{p_{n}\}$ converges to $p \in X$ iff every neighborhood of $p$ contains all but finitely many $p_{n}$
b) If $p \in X$ (Limit points are unique)
c) If $\{p_{n}\}$ converges, then $\{p_{n}\}$ is bounded.
d) If $E$
