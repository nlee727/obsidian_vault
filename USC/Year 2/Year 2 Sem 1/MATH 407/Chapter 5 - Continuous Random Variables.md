## Joint Distributions
Let $f(X,Y)$ denote joint density of $X,Y$. Thus for any set $B$ in the plane, $$
P((X,Y) \in B )=\int  \int_{B}  f(X,Y)\ dx  dy 
$$
Say $X,Y$ are independent if $f(x,y)=f_{X}(x)f_{Y}(y)$ for all $X,Y$
- $E[g(X,Y)]=\int _{-\infty}^\infty \,\int _{-\infty}^\infty g(X,Y)f(X,Y)\, dx dx$

##### Example
Let $(X,Y)$ be uniformly distributed on the set $$
S=\{ (X,Y):0\leq X\leq Y\leq 1\}
$$(triangle)


a) Find joint density of $X$ and $Y$
###### Solution
Uniformly distributes is same as density being constant, so $$
f(X,Y)=\{ c \text{ if }0\leq x\leq y\leq 1, 0\text{ else}\}
$$
Since area of $S=\frac{1}{2}$, must have $c=2$ since $\int  \,\int_{S} f(x,y) \, dx dy=1$
So $f(x,y)=\{2\text{ if } 0\leq x\leq y\leq 1, 0\text{ else}\}$


b) Compute marginal densities $f_{X}(x), f_{Y}(y)$
###### Solution
$f_{X}(x)= \int _{-\infty}^\infty f(x,y)\, dy$


#### Remark
Joint distribution of $X,Y$ considered above is same as $X=min(U,V), Y=max(U,V)$ where $U,V$ are independent uniforms on $[0,1]$.

##### Example
Let $X,Y$ be independent exponentials with parameters $\lambda,\mu$ respectively, calculate $P(X<Y)$.
###### Solution
By independence, the joint density of $X,Y$ is $$
F(x,y)=f_{X}(x)f_{Y}(y) = \lambda e^{-\lambda y}\mu e^{-\mu y} = \lambda \mu e^{-\lambda x-\lambda y}
$$
now $P(X<Y)$ is given by integrating $f(x,y)$ over set $$
S=\{ (x,y):0\leq x\leq y\}
$$
thus,
$$
P(X<Y)=\int  \, \int _{S} \mu e^{-\lambda x-\mu y}\, dx dy 
$$
$$
=\int _{x=0}^\infty \left[ \int _{y=0} ^\infty\,\mu e^{-\lambda x-\mu y} dy  \right]\, dx 
$$
$$
=\int _{x=0}^\infty\left[ \lambda \mu e^{-\lambda x}\int _{y=x}^\infty e^{-\mu y}\, dy  \right] \, dx 
$$
$$
=\int _{x=0}^\infty \lambda e^{-\lambda x-\mu x} \, dx  = \frac{\lambda}{\lambda+\mu}
$$
#### Remarks
1) If $\lambda$ is small, then $X$ tends to be large (since $E(X)=\frac{1}{\lambda}$)
2) If $X$ tends to be large, then $P(X<Y)$ tends to be small

## Sums of Independent Normals
### Theorem
Let $X,Y$ be independent normal($\lambda,\sigma^2$) and normal($\mu,\tau^2$) respectively. Then, $X+Y$ is normal($\lambda+\mu, \sigma^2+\tau^2$).
#### Remarks
- The results extends of more than 2 terms.
##### Example 
Let $X_{1}$ be normal($0,1$), $X_{2}$ be normal($0,4$), $X_{3}$ be normal($0,9$).
Let $X_{1},X_{2},X_{3}$ be independent

a) Find $P(X_{1}+X_{2}+X_{3}<4)$
###### Solution
Let $S=X_{1}+X_{2}+X_{3}$
so $S$ is normal($0,14$)

So $P(S<4)$ = P($\frac{{S-0}}{\sqrt{ 14 }}< \frac{{4-0}}{\sqrt{ 14 }}$)
$=P(z< \frac{4}{\sqrt{ 14 }})=.857$

b) Find $P(4X_{1}-10<X_{2}+X_{3})$
###### Solution
$$
P(4X_{1}-X_{2}-X_{3}<10)
$$
$$
=P(4X_{1}+(-X_{2})+(-X_{3})<10)
$$
Now $X_{1}$ is normal(0,1), $-X_{2}$ is normal($0,4$), $-X_{3}$ is normal($0,9$)
So letting $L=4X_{1}+(-X_{2})+(-X_{3})$, $L$ is normal($0,29$)

variance $16+(-1)^24+(-1)^29=29$

So$P(L<10)=P(z< \frac{10}{\sqrt{ 29 }})=.468$

## Distribution of Sums
$n$ independent Bernoulli(p) random variables $\rightarrow$ binomial($n,p$)
independent Poisson($\mu_{i}$) $\rightarrow$ Poisson($\sum\mu_{i}$)
