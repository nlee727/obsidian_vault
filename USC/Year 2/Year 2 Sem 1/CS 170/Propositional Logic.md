Building blocks of propositional logic are **propositions**
### Definition
A proposition is a declarative sentence that is either true or false but not both

Propositional variables can represent propositions, like p,q,r,s

**Atomic** proposition is one that cannot be expressed in terms of simpler propositions

**Compound** propositions are formed from existing propositions using logical operators

#### Relationship with Boolean Algebra
Propositional logic is an instance of Boolean algebra

#### Conditional Statements
- $p \to q$, if $p$ then $q$
	- False when $p$ is true and $q$ is false
	- True otherwise
- Also called an implication
- p is called the hypothesis/premise
- q is called the conclusion./consequence

- if p then q
- p implies q
- if p, q
- q when p
- p is sufficient for q

The implication is like a promise. The implication is false only if the promise is broken. If the conclusion is true, the implication is true

- $p\to q$ - original
- $\bar{q}\to \bar{p}$ - contrapositive
- $\bar{p} \to \bar{q}$ - inverse
- $q\to p$ - converse

#### Rules of Inference
- $p \text{ is true}, p\to q$, then $q \text{ is true}$
	- Modus ponens
- $p\to q, \bar{q}$. then $\bar{p}$
	- Modus Tollens
- $p\to q, q\to r$, then $p\to r$
	- Hypothetical Syllogism
- $p \cup q,\bar{p}$, then $q$
	- Disjunctive Syllogism
- $p$, then $p\cup q$ 
	- Addition
- $p\cap q$ then $p$
	- Simplification
- $p,q$ then $p\cap q$
	- Conjunction
- $p\cup q, \bar{p}\cup r,$ then $q\cup r$
	- Resolution

### Arguments
- Sequence of statements starting with assumptions and ending with conclusions

### Precents of Logical Operator
1. Not
2. And
3. Or
4. Implication
5. Bi-implication