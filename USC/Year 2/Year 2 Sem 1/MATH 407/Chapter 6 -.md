
#### Definition
$$
cov(X,Y) = E(XY)-E(X)E(Y)
$$
##### Example
Let $X=I_{A} = \{1 \text{ if A occurs, 0 else}\}$
Let $Y=I_{B}$
What is $cov(X,Y)$
$E(X)=1P(I_{A}=1) + 0P(I_{A}=0)=P(A)$
$E(Y)=P(B)$
$E(XY)=E(I_{A}I_{B})$
$=P(I_{A\cap B})=P(A\cap B)$

So $cov(X,Y)=P(A\cap B)-P(A)P(B)$
This is positive $\iff P(A\cap B)-P(A)P(B) >0$
- Call $A,B$ positively dependent
This is zero $\iff(A\cap B)-P(A)P(B) =0$
- Call $A,B$ independent
This is negative $\iff P(A\cap B)-P(A)P(B) <0$
- Call $A,B$ negatively dependent

If $A,B$ are positively dependent, then $P(A\cap B)>P(A)P(B)$ so $P(A|B)>P(A)$ so knowing that $B$ happens makes $A$ more likely and vice versa.

If $A,B$ are negatively dependent, then $B$ happening makes $A$ less likely

##### Example
A box as $b$ black balls and $w$ white balls, where $b,w>0$. Draw 2 balls without replacement.
Let $A = \text{first ball is black}$ $B=\text{second ball is black}$
So $A,B$ are negatively independent

$C=\text{second ball is white}$, then $A,C$ are positively dependent.
If draws are with replacement, then $A,B$ are independent

#### Sign of Covariance
Recall,
$$
cov(XY)=E[(X-\mu_{x})(Y-\mu_{Y})]=E[E(X)E(Y)]
$$
so if above average values of $X$ tend to be associated with above average values of $Y$, and below average values of $X$ are associated with below average values of $Y$, then expect covariance to be positive

For example, pick a random person $X=$ height, $Y=$ weight
Expect that $cov(X,Y)>0$. Similarly, if above average values of $X$ tend to be associated with below average values of $Y$ and below average values of $X$ tend to be associated with above average values of $Y$, expect that $cov(X,Y)<0$
##### Example
$X=$ age of the car, $Y=$ fuel economy of the car
So expect $cov(X,Y)<0$

So we can interpret that sign of $cov(X,Y)$ but its harder to interpret its magnitude

##### Definition
$corr(X,Y)=\frac{cov(X,Y)}{SD(X)SD(Y)}$
Assuming that the $SD(X),SD(Y)>0$

If $corr(X,Y)=0$, say $X,Y$ are uncorrelated. So independent variables are uncorrelated, but uncorrelated doesn't imply independence.

#### Definition
$X^*=\frac{X-\mu_{X}}{SD(X)}$
$Y^*= \frac{Y-\mu_{Y}}{SD(Y)}$
So $X^*,Y^*$ are $X,Y$ rescaled to be in "standard units"
So $E(X^*)=E(Y^*)=0$, $SD(X^*)=SD(Y^*)=1$

#### Theorem
$corr(X,Y)=corr(X^*,Y^*)$
So correlation is a standardized covariance

Also, $-1\leq corr(X,Y) \leq 1$ for any $X,Y$

Correlation of $+1$ indicates a linear relation between $X,Y$ with positive slope.
So $Y=aX+b$ with probability $1$ for some positive $a$.

##### Example
Have a roulette wheel with proportion $r$ of its numbers red $b$ black, and rest green. 
So with $r+b<1$. In many casinos, $r=b=\frac{18}{38}$

Roll the wheel $n$ times. Let $N_{R}=$ number of reds, $N_{B}=$ number of blacks
Calculate $corr(N_{R},N_{B})$

