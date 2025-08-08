2025-08-06 14:14

Status:


Tags:
[[m145]] 
[[uni]] 



___________________________________________________________________________
# m135 - Quantifiers

**Quantified statements:** closes up the size of a statement
- **Quantifier:** “how many” elements of the domain are claimed to make the open sentence true
	- **Universal** → “for all”
		- $\forall$ 
	- **Existential** → “there exists” 
		- $\exists$ 
- **Variable:** any symbol representing a quantity or mathematical object
	- $x$ 
- **Domain:** any set
	- $S$ 
- **Open sentence** (involving the variable): either true or false whenever a value of the variable chosen from the domain is specified
	- $P(x)$ → open sentence involving variable $x$ 
	- Truth of $P(x)$ represents $x$ having “property” $P$ 
- *Example:* For all integers $n\geq 5$, $2^{n}\geq n^{2}$. 
- *Writing mathematically:* 
	- $\forall x\in S, P(x)$ → “For all $x$ in $S$, $P(x)$ (is true)”
		- The entire statement is true when $P(x)$ is true for all $x$ in $S$ 
	- $\exists x\in S, P(x)$ → “There exists at least one value of $x$ in $S$ for which $P(x)$ (is true)”
		- The entire statement is true when $P(x)$ is true for at least one element $x$ in $S$  

**Negation of Quantifiers:** 
- $\neg (\forall x\in S, P(x))\equiv (\exists x\in S, \neg P(x))$ 
	- Negation of “For all $x$ in $S$, $P(x)$ is true” is “There exists some $x$ in $S$ for which $P(x)$ is false” 
- $\neg (\exists x\in S, P(x))\equiv (\forall x\in S, \neg P(x))$ 
	- Negation of “There exists some $x$ in $S$ for which $P(x)$ is true” is “For all $x$ in $S$, $P(x)$ is false”

**Nested Quantifiers:** when a statement has more than 1 quantifier (each associated with a variable and domain) → order matters
- I.e. $\forall s\in \mathbb{R}, \exists t\in \mathbb{R}, t>s$ → true
	- For all $s$ in real numbers, there exists a $t$ such that $t$ is greater than $s$ 
- **Not logically equivalent** to $\exists t\in \mathbb{R}, \forall s\in \mathbb{R}, t>s$ → false
	- Impossible for $t$ to be bigger than $s$ guaranteed for all cases in the real numbers
- If you have sets $X$ and $Y$ and open sentence $Q(x,y)$ whose truth values can be determined from the sets:
	- Two universal quantifiers are equivalent
	- Two existential quantifiers are equivalent
	- One universal and one existential quantifier is not equivalent 
- For 3+ → think of them being parathensized where each inner statement corresponds to another open sentence

**Negation of Negative Quantifiers:** 
- $\neg \exists x\in X, (\forall y\in Y, (\exists z\in Z, R(x,y,z)))\equiv \forall x\in X, (\exists y\in Y, (\forall z\in Z, \neg R(x,y,z)))$  
	- ==Switch the universal and existential quantifiers + Negation on the very outside is equal to negation on the very inside== 
- Still turns true to false and vice versa












# References

