
### Definition
Let a sample space  $S=$ outcomes of an experiment
##### Example
1. The gender of a newborn child $S=\{g,b\}$
2. Toss a coin twice $S=\{(H,H),(H,T),(T,H,),(T,T)\}$
3. Lifetime of a lightbulb in hours $S=\{x: 0\leq x\leq \infty$
4. Ranking of 3 people in a long jump competition $S=\{\text{all permutations of } 1,2,3\}$

#### Definition
An event $E$ is a subset of the sample space

1. $E=\{b\}$ is the event that child is a boy
2. $E=\{(1,1,5),(2,2,5),(3,3,5)$
4. $E=\{1\leq x \leq 2.5\}$ is the event that the bulb lasts at most 2.5 hours

#### Definition
$E \vee  F$=outcomes in $E$ or in $F$ or in both $E$ and $F$

1. Let $E=(T,H),(T,T)$
	Let $F = (H,T),(T,T)$
so $$
E \vee F = (T,H),(T,T),(H,T)
$$
##### Example: 
Roll a dice $3$ times 

Let $E=(1,1,2),(1,1,3),(1,2,4)$
	$F=(2,1,1),(2,2,2)$

Then $E \cap F= 0$

In general, if $E,F$ are events, with $E\cap F=0$, then $E$ and $F$ are mutually exclusive

Similarly,
$$
\vee_{n=1}^{\infty}
$$
is union of $E_{1},E_{2},\dots$

### Definition
Given an event $E$, let $E^C=$ "Complement" of $E=$ elements of $S$ not contained in $E.$

##### Example
Toss a coin twice,
$$
S=\{(H,H),(H,T),(T,H),(T,T)\}$$
Let $E=(H,H)$ 2 heads
Then $E^C=\{(H,T),(T,H),(T,T)\}$ at least 1 tail

### Definition
If all outcomes in $E$ are in $F$, say $E$ is contained in $F$ and write $E \subset F.$

If $E\subset F$ and $F\subset E$, say $E=F$

#### Properties
$$
E\cup F=F\cup E
$$
$$
E\cap F=F\cap E
$$
$$
(E\cup F)\cup G=E\cup(F\cup G)
$$
$$
(E\cap F)\cap G=E\cap(F\cap G)
$$
##### Example
Prove that $$
(E\cap F)\cup G=(E\cup G)\cap(F\cup G)
$$
- Step 1
	- Show that $(F\cap F)\cup G \subset(E\cup G)\cap(F\cup G)$
- Step 2
	- Show that $(E\cup G)\cap(F\cup G)\subset(E\cap F)\cup G$

#### Demorgan's Laws
1. 
$$
(\cup_{i=1}^nE_{i})^c=\cap_{i=1}^n(E_{i}^c)
$$
2. 
$$
(\cap_{i=1}^nE_{i})^c=\cup_{i=1}^n(E_{i}^c)
$$

### Axioms of Probability
1. $0\leq p(E)\leq 1$ for all $E$
2. $p(S)=1$
3. If $E_{1},E_{2},\dots$ are mutually exclusive, then $P(\cup_{i}E_{i})=\sum_{i}P(E_{i})$

### Theorem
For any events $E$ and $F$, 
$$P(E\cup F)=P(E)+P(F)-P(E\cap F)
$$

#### Principle of Inclusion and Exclusion
For any events $E,F,G$
$$
P(E\cup F\cup G)=P(E)+P(F)+P(G)-P(E\cap F)-P(E\cap G)-P(F\cap G)+P(E\cap F\cap G)
$$

## Theorem
For any events $E_{1},E_{2},\dots,E_{n}$
$$
P(E_{1},\cup\dots \cup,E_{n})=\sum_{i}P(E_{i})-\sum_{i_{1}<i_{2}}P(E_{i_{1}}\cap E_{i_{2}})+(-1)^{r+1}+\sum_{i_{1}<i_{2}<\dots i_{r}}P(E_{i_{1}}\cap E_{i_{2}}\dots \cap E_{i_{r}})
$$

##### Remark
$$
P(E_{1}\cup\dots E_{n})\leq \sum_{i=1}^nP(E_{i})
$$
$$
P(E_{1}\cup\dots E_{n})\geq \sum_{i=1}^nP(E_{i})-\sum_{i<j}P(E_{i}\cap E_{j})
$$
$$
P(E_{1}\cup\dots E_{n})\leq \sum_{i=1}^nP(E_{i})-\sum_{i<j}P(E_{i}\cap E_{j})+\sum_{i<j<c}P(E_{i}\cap E_{j}\cap E_{c}) \text{ etc.}
$$
#### Sample Spaces with equally likely outcomes
Suppose all outcome in the sample space are equally likely. Then for any event $E,$ $$
P(E)=\frac{\text{Number of outcomes in E}}{\text{Number of outcomes in S}}
$$

###### Remark
If you forget about the ordering of the rolls, then (3,5) and (5,3) are the same outcome. But then all outcomes aren't equally likely. Its useful to do things sequentially

##### Example
Have $n$ people in a room. Find $P($all have distinct birthdays$)$

How large does $n$ have to be so that this probability is less than $\frac{1}{2}$?

Assume each year has 365 days and all birthdays are equally likely

###### Solution
The chance that $n$ people have distinct birthdays is
$$
\left( \frac{365}{365} \right)\left( \frac{364}{365} \right)\left( \frac{363}{365} \right)\left( \frac{{365-n+1}}{365} \right)
$$
###### Remark
There are many variations on birthday problem, for example,
- What happens if birthdays aren't equally likely
- How large does $n$ have to be so that $P($ 3 people have same birthday) $= \frac{1}{2}$?

##### Example
Have $n$ people with distinct hats. Randomly permute the hats. Find 
$$
P(\text{No one gets their hat back})
$$
###### Solution
Let event $E_{i}$ be the event that person $i$ gets their hat back
By inclusion-exclusion, $P(\text{at least one person gets their hat back)}$ 
$$
=P(\cup_{i=1}^n)E_{i}
$$
$$
\sum_{i=1}^nP(E_{i})-\sum_{i_{2}<i_{2}}P(E_{i_{1}}\cap E_{i_{2}})\dots+(-1)^{n+1}\lambda(E_{i_{n}}\cap\dots E_{n})
$$
Observe that for any $r$ and $i_{1}<i_{2}<\dots<i_{n}$
$$
P(\text{People i1, i2, get their hats back}) = \frac{{n-r}!}{r!}
$$
And there are $(^n_{r})$ terms of this form.


So $P(\text{No one gets their hat back)}$ = $1-P(\cup_{i=1}^nE_{i})$




