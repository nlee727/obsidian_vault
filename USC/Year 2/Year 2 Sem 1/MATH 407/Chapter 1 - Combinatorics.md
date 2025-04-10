### Basic Counting Principles
Perform 2 experiments
- If experiment 1 has $m$ possible outcomes and experiment 2 has $n$ possible outcomes, then the total number of outcomes is $n\cdot m$
- If you have $r$ experiments, the $i$th of which has $n_{i}$ possible outcomes, then the total number of outcomes is $n_{1}\cdot n_{2}\cdot \dots n_{r}$

##### Example
How many 7 plate license plates are possible if the first 2 are letters and last 5 are numbers

$$
26\cdot 26 \cdot 10\cdot 10\cdot 10\cdot 10\cdot 10
$$
What if no number can be used more than once?
$$
26\cdot 25 \cdot 10\cdot 9\cdot 8\cdot 7\cdot 6
$$

##### Example
Roll a die 4 times
How many possible outcomes are there?
$$
6\cdot 6\cdot 6\cdot 6
$$

### Permutations
How many different ordered arrangements of $1,2,3$ are possible?
$$
6
$$
##### Example
John, Jim, Jay, and Jack form a band with $4$ instruments
1. If each of them can play any instrument, how many arrangements are possible?
$$
4!
$$
2. What if John and Jim can play any instrument, but Jay and Jack can play play piano and drums?
$$
4
$$
##### Example
In how many ways can 3 boys and 3 girls sit in a row?
$$
6!
$$
What if boys must sit together and girls must sit together?
- 2 cases
$$
3!\cdot 3! \cdot 2
$$
What if only boys must sit together?
- 4 cases
$$
3! \cdot 3! \cdot 4
$$
What if no 2 people from the same gender can sit next to each other?
- 2 cases
$$
3!\cdot 3! \cdot 2
$$
##### Example
How many length $9$ orderings are there which use two 1's, four 2's , and three 3's

###### Solution
Let $S_{9}=$ all permutations of $1,2,\dots, 9$
Define a map $f:$ $S_{9}\to$ two 1's, four 2's , and three 3's

Given an element of $S_{9}$, 
put 1's in positions of 1,2
put 2's in positions of 3,4,5,6
put 3's in positions of 7,8,9

For example
$$
f:1 73425876\to 132212332
$$
Every ordering with two 1's, four 2's , and three 3's is hit my some permutation
- In each such ordering, is mapped to $2! \cdot4! \cdot3!$ many permutations.
- Thus, the number of possible orderings is $\frac{9!}{{2!\cdot 4!\cdot 3!}}$

#### Property:
The same reasonings shows that the number of permutations of $n$ objects, of which $n_{1},n_{2},\dots,n_{r}$ are alike is $$
\frac{n!}{n_{1}!\cdot n_{2}! \cdot\dots \cdot n_{r}!}
$$
##### Example
How many different arrangements can be made from the letters in the following words, where you regard capital and lowercases the same?
1. Fluke
$$
5!
$$
2. Propose
$$
\frac{7!}{{2!\cdot 2! \cdot 1! \cdot 1! \cdot 1! \cdot 1! \cdot 1!}}
$$
3.  Mississippi
$$
\frac{11!}{{4! \cdot 4! \cdot 2! \cdot 1!}}
$$

### Combinations
Number of ways to choose $n$ objects from $m$ distinct objects 
#### Notation
Let $(^n_{r})$ denote $\frac{n!}{r!(n-r)!}$ this is called a binomial coefficient and $0! =1$

##### Example
Have a class of 30 students. Have 5 awards.
How many award outcomes are possible if

1. A student can receive any number of awards
$$
30\cdot 30 \cdot 30 \cdot 30\cdot 30
$$
2. A student can get at most 1 award
	1. Solution 1 $$
30 \cdot 29 \cdot 28\cdot 27\cdot 26
$$
	2.  Solution 2
$$
(^{30}_{5})
$$
Then you have 5! ways to distribute the awards to the 5 students
$$
(^{30}_{5})5!
$$

##### Example
Have a room with 20 people, everyone shakes hands with everyone else.
How many handshakes take place?
$$
(^{20}_{2})
$$

##### Example
How many 5 card poker hands are there?
$$
(^{52}_{5})
$$
##### Example
Student has to sell 2 books from a collection of 6 math, 7 science, and 4 economics books.
How many choices are possible if 

1. Both books the same subject
$$
(^6_{2})+(^7_{2})+(^4_{2})
$$
2. Both books are different subjects
$$
(6\cdot 7)+(6\cdot 4)+(7\cdot 4)
$$
	or
$$
(^{17}_{2}) -42 (\text{ answer to a })
$$

##### Example
There are $n$ balls. $k$ are red, $n-k$ are white. All balls are indistinguishable
How many ways can you line up the balls such that no 2 red balls are adjacent?

Have $n-k+1$ positions where you could put the red balls and $k$ red balls
$$
(^{n-k+1}_{k})
$$

#### Property
$$
(^n_{r})=(^{n-1}_{{r-1}})+(^{n-1}_{r})
$$
if $1\leq r\leq n$
and $(^{n-1}_{n})=0$

### Binomial Theorem
$$
(x+y)^n
=\sum^n_{k=0}(^n_{k})x^ky^{n-k}$$

The coefficient of $x^ky^{n-k}$ is the product

##### Example
Expand $(3x^2+y)^5$

$$
(3x^2+y)^5=\sum^5_{k=0}(3x^2)^ky^{5-k}
$$
$$
= (^5_{0})y^5+(^5_{1})3x^2y^4 +(^5_{2})9x^4y^3
+(^5_{3})27x^6y^2+(^5_{4})81x^8y+(^5_{5})243x^{10}$$

#### Multinomial Coefficients
Have $n$ distinct items. How many ways can divide them into $r$ groups if the $i$th group has size $n_{i}$ and $n_{i}+\dots+n_{r}=n$

Number of choices for group 1 is $(^n_{n_{1}})$. 
Then number of choices for group 2 is $(^{n-1}_{n_{2}})$. 
Then the numbers of choices for group 3 is $(^{n-n_{1}-n{2)}}_{n_{3}})$

So final number is

$$
(^n_{n_{1}})(^{n-n_{1}}_{n_{2}})(^{n-n_{1}-n{2)}}_{n_{3}})\dots
$$
$$
=\frac{n!}{{n_{1}!}n_{2}!n_{3}!\dots n_{r}!}
$$
The special case $r=2$ is a binomial coefficient

##### Solution 2
$n$ items. Group item is in $2,3,3,\dots 2$

So answer is the number of words of length $n$ consisting of $n_{1}$ 1's, $n_{2}$ 2's, etc.

#### Notation
$$
(^n_{n_{1},n_{2},\dots n_{r}})
=\frac{n!}{n_{1}!n_{2}!\dots n_{r}!}$$

##### Example
Need to divide 12 people into committees of size $3,4,5$. In how many ways can you do this?

$$
(^{12}_{3\quad 4\quad 5})
$$

#### Number of Integers
$$
x_{1}+\dots+x_{r}=n
$$
if all $x_{i}>0$
$$
(^{n-1}_{r-1})
$$
if all $x_{i} \geq 0$
$$
(^{n-r-1}_{{r-1}})
$$


##### Example
If 8 identical blackboards are to be given to 4 different schools how many divisions are possible?

$$
x_{1}+x_{2}+x_{3}+x_4=8
$$
$$
(^{8+4-1}_{3}) = (^{11}_{3})
$$

What if each school must get at least 1 blackboard
$$
x_{1},x_{2},x_{3},x_{4}
$$
are positive integers, thus from last time, the number of solutions is
$$
(^{8-1}_{4-1})=(^7_{3})=35
$$

##### Example
An elevator starts from the basement with 8 people (not including the operator). There are 6 floors.

1. In how many ways can the operator perceive leaving the elevator if all people look the same to the operator?
We seek the number of solutions to $x_{1}+\dots {x_{6}}=8$ where $x_{1},\dots ,x_{6}$ are nonnegative integers
$$
(^{8+6-1}_{{6-1}})=(^{13}_{5})
$$
2. What if there are $5$ men and $3$ women and the operator can distinguish the men from the women?
Take possibilities for the men and multiply for the women

For men, from $x_{1}+\dots x_{6}=5$ for all $x_{i}\geq 0$
$$
(^{5+6-1}_{6-1})
$$
For women count solutions to $x_{1}+\dots x_{6} =3$ for all $x_{i}\geq 0$
$$
(^{3+6-1}_{6-1})
$$
