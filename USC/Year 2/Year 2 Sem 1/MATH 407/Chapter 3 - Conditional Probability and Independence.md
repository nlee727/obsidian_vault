##### Example
Toss a coin 3 times let $A$ be the event that you get 2 or more heads
HHT,HTH,THH,HHH
So $P(A) = \frac{4}{8}$
$B$= First toss is head
Then $P(A|B)$ = $P(\text{At least 1 head in the last 2 tosses})=$$\frac{3}{4}$

$$
P(A|B) =\frac{{A\cap B}}{B}
$$
##### Example
Roll a die twice, find $P()$ First roll is a 6, Sum of the rolls is $i$, for all $i$

###### Solution
If $i=2,3,\dots 6$, then $P(E\cap F)=0$

If $i=7,$ $P(E\cap F)=\frac{1}{36},P(F)=\frac{6}{36},P(E|F)=\frac{1}{6}$

If $i=8,$ $P(E\cap F) = \frac{1}{36}, P(F)=\frac{5}{36}, P(E|F)=\frac{1}{5}$

$$
P(E\cap F)=P(F)P(E|F)
$$

##### Example
Consider a family with 2 children. Given that at least one of children is a boy, whats the chance both are boys?

###### Solution 1
Let $E$ = both are boys
Let $F$ = at least 1 boy

so $$
P(E|F)=\frac{P(E\cap F)}{P(F)} = \frac{{\frac{1}{4}}}{\frac{3}{4}}=\frac{1}{3}

$$
##### Example
Mr. Smith has 2 children. You meet him walking with a boy who is his son. What's the chance his other child is also a boy?


#### Averaging Conditional Probabilities
$$
P(A)=P(A|B)\cdot P(B)+P(A|B^c)\cdot P(B^c)
$$
### Bayes' Formula
Let $S$ = sample space
Have events $H_{1},H_{2},\dots H_{m}$ that pairwise disjoint $(H_{i}\cap H_{j}=\emptyset$ if $i\neq j)$
and such that $S=H_{1}\cup H_{2}\cup\dots \cup H_{m}$
Call $H_{1},\dots,H_{m}$ the hypothesis.
Have an event $E$ which gives some information about which hypothesis is correct.
Call $E$ the **evidence**

Before you set the evidence, have prior probabilities $P(H_{1}),\dots P(H_{m})$ for the hypothesis.
Also if you know which hypothesis is correct, then you know the probability of the evidence.

In other words, you know $P(E|H_{i})$ for all $i$.
Want to compute $P(H_{i}|E)$, which are called "posterior probabilities"


$$
P(H_{i}|E)=\frac{{P(H_{i})\cdot P(E|H_{i})}}{\sum_{k=1}^mP(H_{k})\cdot P(E|H_{k})}
$$
$H_{i}$ is the prior

### Independence
$E,F$ are independent, $P(E|F)=P(E) \iff P(E\cap F)=P(E)\cdot P(F)$
#### Proposition
$E,F$ are independent $\rightarrow$ $E,F^c$ are independent
#### Mutually Independent
$A_{1},A_{2},\dots,A_{n}$ are mutually independent if for any subset $I\subset \{1,2,\dots,n\}$
$$
P(\cap_{i \in I}A_{i})= \Pi_{i \in I}P(A_{i})
$$
