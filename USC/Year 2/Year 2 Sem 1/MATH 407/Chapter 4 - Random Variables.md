For $n$ Bernoulli $(p)$ random variables, have an event with success probability $p$ and failure probability $q,$ where $q=1-p$.

#### Examples
Flip a coin
- Heads is success
- Tails is failure
- $p =0.5,q=0.5$

Roll a die
- 6 is success
- 1,2,3,4,5 are failures
- $p=\frac{1}{6},q=\frac{5}{6}$

### Binomial Distribution
For $n$ independent trials, each with success probability $p$ and failure probability $q=1-p$, the chance of exactly $k$ successes is $$
(^n_{k})p^kq^{n-k}
$$
#### Example
Toss a fair coin $n$ times
Find $P(\text{get exactly k heads})$
$$
(^n_{k}) \frac{1}{2}^k \frac{1}{2}^{n-k}
$$
Find $P(\text{4 or more heads in 6 tosses of a fair coin)}$
$$
(^6_{4}) \frac{1}{2}^4 \frac{1}{2}^{6-4}
$$
#### Example
Find probability that among $5$ families, each with $6$ children, at least $3$ of families have $4$ or more girls

By a previous example, the chance that a given family has $4$ or more girls is $(^6_{4}) \frac{1}{2}^4 \frac{1}{2}^{6-4} = \frac{11}{32}$
Call this a "success". We want the probability of at least $3$ successes in $5$ trials.
$$
=(^5_{3}) \frac{11}{32}^3 \frac{21}{32}^{5-3}+(^5_{4}) \frac{11}{32}^4 \frac{21}{32}^{5-4}+(^5_{5}) \frac{11}{32}^5\frac{21}{32}^{5-5} = .226$$
### Remarks
1) Most likely number of successes is called the mode of the binomial distribution with parameters $n,p$, where $n=$ number of trials, $p=$probability of success of each trial

The mode $m=$ Greatest integer $\leq np+p$ 

If $np+p$ is an integer, as in the case $p=\frac{1}{2}$, $n$ odd, then there are $2$ modes $m$ and $m-1$ otherwise there's a unique mode.

In either case, the probabilities for the binomial distribution are increasing until the mode is hit, and then are decreasing.

2) Expected number of successes = "mean" of binomial distribution
$$
\mu=np
$$
3) Normal Curve
$\mu=$mean
$\sigma=$ standard deviation
Normal curve is given by $$
\frac{1}{\sqrt{ 2 }\pi \sigma}e^{-(x-\mu)^2/2\sigma^2}, -\infty <x<\infty
$$
define $\Phi(z)=\text{area to left of z under a standard normal curve}$
$\Phi(z)$ is called the "cumulative distribution function"

#### Remarks
1) By the symmetry of the normal curve, if $z\geq 0,$ then $\Phi(-z)=1-\Phi(z)$.
2) The probability of being in the interval $(a,b)$ is $\Phi(b)-\Phi(a)$, so note for $z \geq 0$ $P=z\Phi(z)-1$

$$
\Phi(1)-\Phi(-1)\approx.68
$$
$$
\Phi(2)-\Phi(-2)\approx.95
$$
$$
\Phi(3)-\Phi(-3)\approx.997
$$
#### Normal Distribution to Binomial Distribution
Perform $n$ independent trials each with success probability $p$. Let $X$ be the number of successes, so $X$ is binomial$(n,p)$.
Then we have the approximation:
For integers $a <b$,
$$
P(a \leq X\leq b) \approx \Phi\left( \frac{{b+\frac{1}{2}-\mu}}{\sigma} \right)-\Phi\left( \frac{{a-\frac{1}{2}-\mu}}{\sigma} \right)
$$
where $\mu=np,\sigma=\sqrt{ npq },$
##### Example
Toss a fair coin 100 times, approximate $P(\text{exactly 50 heads})$
$$
\frac{(^{100}_{50})}{2^{50}}
$$
so $P(50\leq X\leq 50)\approx \Phi\left( \frac{{50+\frac{1}{2}-50}}{5} \right)-\Phi\left( \frac{{50-\frac{1}{2}-50}}{5} \right)$
$$
=\Phi(.1)-\Phi(-.1)=1-\Phi(.1) = .0796
$$
$P(45\leq X\leq 55)$
$$
\approx \Phi(55.5-50)
$$
#### Poisson approximation to binomial
Let $X$ be binomial$(n,p)$. So $X$ is the number of successes in $n$ independent trials each with success probability $p$.

(Coin tossing is $p=\frac{1}{2}, n$ large, then use normal approximation) If $p$ is small, normal approximation is poor.

For $p$ small, $n$ large, let $\mu=np$. Then can approximate by a poisson distribution with parameter $\mu$ by
$$
P(x=k)\approx \frac{1}{e^\mu} \frac{\mu^k}{k!}
$$
#### Remarks
1. Works well for small $p$ error in approximation depends mostly on $p$ and not on $n$
2. Sketch a proof of why $P(x=k)\approx \frac{1}{e^\mu} \frac{\mu^k}{k!}$ is true.

##### Example
Suppose a manufacturing process produces $1\%$ defective items. Approximate chance of getting $2$ or more defective items in a sample of $200$ items produced by the process

Could use binomial $(200,0.01)$. Let's see what Poisson approximation gives. Let $X$ be Poisson(200X,0.01)= Poisson($2$) 

So $P(\text{2 or more defective items}$ $\approx P(x\geq 21)$
$$= 1 - P(X>0)-P(X=1)
$$
$$
=1-\frac{1}{e^2} \frac{2^0}{0!}-\frac{1}{e^2} \frac{2^1}{1!}
$$
$$
= .594
$$
#### Remark
$$
\sum_{k\geq 0} \frac{1}{e^\mu} \frac{\mu^k}{k!}
$$
$$
=\frac{1}{e^\mu} \sum_{k\geq 0} \frac{\mu^k}{k!}
$$



#### Sampling With and Without Replacement
Have a population of size $N$, with $G$ good and $B$ bad elements
### Theorem
For a sample of size $n=g+b$ with $0\leq g\leq n$, the chance of getting $g$ good elements and $b$ bad elements is...
- For sampling with replacement
$$
(^n_{g})\frac{G^gB^b}{N^n}
$$
- For sampling without replacement get
$$
\frac{(^G_{g})(^B_{b})}{(^N_{n})}
$$
### Random Variables
The number of heads in $4$ tosses of a fair coin can be $0,1,2,3,4$. A random variable is something like this: It can take a range of values with certain probabilities. So in this example, let $X$ be the number of heads.

Then $$
 P(X=i)= \frac{(^4_{i})}{2^4}
$$
Usually capital letters denote random variables
Note: random variables don't have to be numbers. For example let $X$ be the suit of a random card.

So usually random variables will be real numbers.

#### Joint Distribution
Say $(X,Y)$ has value $(x,y)$ if $X=x$ and $Y=y$. The distribution of $(X,Y)$ is called the joint distribution of $X$ and $Y$.

A box contains the numbers $1,2,3.$ Let $X$ and $Y$ be the first and second draws from this box where draws are without replacement.

#### Probability of events determined by X and Y
The probability that $X,Y$ satisfy some condition is the sum of $P(x,y)$ over all $(x,y)$ satisfying the condition. Here, $P(x,y)=P(X=x,Y=y)$

For example,
$$
P(X<Y)=\sum _{x<y}P(x,y)
$$
The distribution of any function of $X$ and $Y$ can be obtained form joint distribution of $X$ and $Y$.

For example,
$$
P(X+Y=z)=\sum_{(x,y)\text{ such that x+y=z}}P(x,y)
$$
##### Example
Calculate distribution of $X+Y$ for the random draws $X,Y$ from a box containing the numbers $1,2,3$
1. Without replacement
2. With replacement

#### Remark
This shows that to study the distribution of $X+Y$ you need to know about the joint distribution of $X$ and $Y$. Its not enough to know that $X,Y$ are uniform on {$1,2,3$}

### Definition
Random variables $X,Y$ are called independent if $P(X=x,Y=y)=P(X=x)\cdot P(Y=y)$ for all $x,y$
### Theorem
If $X,Y$ are independent, then all sets $A,B$
$$
P(X \in A \text{ and } Y \in B) = P(X \in A) \cdot P(Y \in B)
$$

##### Remark
For possible values of $X,$ as $y$ ranges over the range of $Y$, the probabilities $P(Y=y|X=x)$ define a probability distribution on the range of $Y$. This is called the conditional distribution of $Y$ given that $X=x$. 

Then
$$
X,Y \text{ are independent }\iff \text{the conditional distribution of Y given X=x doesn't depend on X}
$$
###### Addition Rule for Expected Values
For any 2 random variables $X$ and $Y$,
$$
E(X+Y)=E(X)+E(Y)
$$
This is true even if $X,Y$ aren't independent.
Similarly,
$$
E(X_{1}+\dots +X_{n})=E(X_{1})+\dots+E(X_{n})
$$
#### Method of Indicators
Recall that if $I_{A}$ is the indicator of an event $A$, then $E(I_{A})=P(A)$
##### Example
Suppose a system has $n$ components, and that at a certain time, the chance of $j$th componenet working is $P_{j}$ Let $X=$ number of components working at that time
Find $E(X)$

Write $X=I_{1}+\dots+I_{n}$ where $I_{j}=1$ if $j$th component is working and $I_{j}=0$ else.

Then $E(X)=E(I_{1})+\dots+E(I_{n}) = p_{1}+\dots p_{n}$

### Markov's Identity
If $X\geq 0$, then for all $a>0,$ $$
P(X\geq a) \leq \frac{E(X)}{a}
$$
where $X$ is a real valued random variable

##### Expected value of a function of a random variable X
Usually,
$$
E(g(x)) \neq g[E(X)]
$$
Instead,
$$
E(g(x))=\sum_{x}g(x)P(X=x)
$$
For example, if $g(x)=x^k$ then you get $E(x^k)=\sum_{x}x^k(P(X=x)$
This is called the kth moment of the random variable $X$
##### Example
If $c$ is a constant, $$
E(cX)=cE[X]
$$
in this case $g(x)=cx$

##### Example 2
Let $X$ be uniform on $\{-1,0,1\}$
so $P(X=-1)=P(X=0)=P(X=1)=\frac{1}{3}$

Thus,
$$
E(X)=\frac{1}{3}(-1)+\frac{1}{3}(0)+\frac{1}{3}(1)=0
$$
$$
E(X^2)=\frac{1}{3}(-1)^2+\frac{1}{3}(0)^2+\frac{1}{3}(1)^2
$$
Therefore $E(X^2) \neq E(X)^2$

More generally, for a function $g$ of $X$ and $Y$,
$$
E(g(X,Y))=\sum_{x,y}g(x,y)P(X=x,Y=y)
$$
Now we can prove addition rule for expected values:
$$
E(X+Y)=E(X)+E(Y)
$$
### Theorem
If $X,Y$ are independent, then $E(X,Y)=E(X)E(Y)$

#### Standard deviation and normal approximation
The variance of $X$, denoted $var(X)$ is defined as the mean, square deviation of $X$ from its expected value

so $var(X)=E[(X-\mu)^2]$ where $\mu=E(X)$
$$
var(X)=E(X^2)-E(X)^2
$$
$$=\sum_{x}x^2P(X=x)-(\sum_{x}P(X=x))^2
$$

$SD(X)$ is $\sqrt{ var(X) }$

##### Remark
$SD(X)$ measures how spread out the distribution of $X$ is around its mean.
$var(X)$ is harder to interpret, but has nicer algebraic properties

#### Remarks
1) If $X$ is approximately normal, the chance of being within one standard deviation of the mean is roughly $.68$
2) If $X$ isn't normal there's no simple way to visualize $SD(X)$. But for any $X,$ $X$ is likely to be within a few standard deviations of it's expected value. We'll make this precise using "Chebyshev's inequality"
3) Like $E(X)$, the standard deviation $SD(X)$ can be interpreted in terms of a sum $S_{n}=X_{1}+\dots+X_{n}$ where $X_{i's}$ are independent each with the same distributions as $X$. What happens is that $S_{n}$ is approximately normal with parameters in terms of $n_{1}E(X_{1})SD(X)$. We will call this the central limit theorem

##### Example
Random Sampling
A box contains $n$ tickets labeled $X_{1},\dots,X_{n}$. Pick a random ticket from the box and let $X$ be the result.
Then $\frac{E(X)=x_{1}+\dots+x_{n}}{n}$ also called $\bar{x}$
$var(X)=\frac{1}{n}\sum_{i}(x_{i}-\bar{x})^2$
$= E(x^2)-(\bar{x})^2=\frac{(x_{1})^2+\dots+(x_{n})^2}{n}-(\bar{x})^2$

##### Example
Indicators
Suppose $X$ is the indicator of an event with probability $p$, so $P(X=1)=p$ and $P(X=0)=1-p$

Find $SD(X)$
We know from before $$
E(X)=1p(X=1)+0p(X=0) = p
$$
Since the only value $X$ can take is $0$ or $1$, it follows that $X^2=X$
Thus $E(X^2)=E(X)=p$
so $var(x)=E(x^2)-[E(x)]^2$
$=p-p^2=p(1-p)$
So $SD(X)=\sqrt{ p(1-p) }$

#### Scaling and Shifting
For constants $a$ and $b$, $SD(aX+b) = |a|SD(X)$
so shifting by $b$ doesn't change the standard deviation and rescaling by $a$ multiplies it by $|a|.$
$$
E(xX+b)=aE(X)+b
$$
#### Standardization
Given an random variable $X$, its often convenient to study the standardized version $X^*$ which tells you how many standard deviations $X$ is from its mean.

More precisely if $E(X)=\mu$ and $SD(X)=\sigma>0$ then $$
X^* = \frac{{X-\mu}}{\sigma}
$$
Any event determined by the value of $X$ can be written in terms of $X^*.$ Usually this is done by manipulating inequalities.

## Chebyshev's Inequality
For any random variable $X$ and $k > 0$
$$
P(|X-E(X)|\geq k \text{ } SD(X)) \leq \frac{1}{k^2}
$$
The chance that $X$ is at least $k$ standard deviations away from its mean is at most $\frac{1}{k^2}$

### Law of Averages
Let $x_{1},\dots x_{n}$ be independent each with the same distribution as a random variable $X$.
Let $\mu=E(X)$ and $\bar{X_{n}}=\frac{{X_{1}+\dots X_{n}}}{n}$
, no mat
Then for every fixed $\epsilon > 0$, no matter how small,
$$
P(|\bar{X_{n}}-\mu|< \epsilon) \rightarrow 1
$$
as $n \rightarrow \infty$

## Central Limit Theorem
Let $X_{1},\dots,X_{n}$ be independent, each with the same distribution over a finite set of values.
Let $Sn=X_{1}+\dots X_{n}$
Let $\mu=E(X_{i}),\quad \sigma=SD(X_{i})\neq 0$

Then for $n$ large, $S_{n}$ is approximately normal with mean $E(S_{n})=n\mu$  and $SD(S_{n})=\sqrt{n}\sigma$.

That is to say, for all $a \leq S,$ 
$$
P\left( a \leq \frac{S_{n}-n\cdot \mu}{\sigma \sqrt{ n }}  \leq b\right)
$$
#### Recall Poisson Distribution
Poisson approximation is useful for counting the number of successes when you have lots of trials each small success of probability. And trials are approximately independent.

For example, if $X$ is binomial and $np \rightarrow \mu$ 
then $X \rightarrow \text{poisson}(\mu)$

##### Features of a Poisson distribution
$E(X)=np$
$X \rightarrow \text{poisson}(\mu)$
So a $\text{poisson}(\mu)$ random variable has mean $\mu$.

Similarly
$SD(X)=\sqrt{ np(1-p) }$
$=\sqrt{ \mu }$
as $n\rightarrow\infty$ and $p\rightarrow 0$ , $np \rightarrow \mu$

### Theorem
If $N$ is $\text{Poisson}(\mu)$ then $E(N)=\mu$, $SD(N)=\sqrt{ \mu }$

##### Remarks
Let $N_{\mu}$ be poisson($\mu$)
1) For large $\mu_{1}$
$$
\frac{{N_{\mu}-\mu}}{\sqrt{ \mu  }}
$$
Is approximately normal
2) Since $$E\left( \frac{N_{\mu}}{\mu} \right)=\frac{1}{\mu}E(N_{\mu})=\frac{1}{\mu}\mu=1$$
$$
SD\left( \frac{N_{\mu}}{\mu} \right)=\frac{1}{\mu}SD(N_{\mu})=\frac{1}{\mu}\sqrt{ \mu }=\frac{1}{\sqrt{ \mu }}
$$
So for $\mu$ large, $SD(\frac{N_{\mu}}{\mu})$ is small. So expect $\frac{N_{\mu}}{\mu}$ to be close to $1$ with high probability can make this precise using Chebyshev's inequality.

## Theorem
Let $n_{1},\dots,n_{j}$ be independent Poissons with parameters $\mu_{1},\dots,\mu_{j}$.
Then, the sum of $n_{1}+\dots + n_{j}$ is Poisson$(\mu_{1}+\dots+\mu_{j})$


