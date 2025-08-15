2025-08-14 11:59

Status:


Tags:
[[m145]]  
[[uni]] 


_______
# m135 - Sets

**Useful:** 
- [[m135 - Sets Introduction]] 
- [[m135 - Set Operations]] 
- [[m135 - Subsets]] 
- [[m135 - Set Equality and Implications]] 

**Definition:** 
- **Empty set:** set that contains no elements
	- $\emptyset=\{ \}$   
	- *Note* → $\emptyset \neq \{\emptyset \}$ → second contains the element of an empty set
- **Cardinality:** number of elements in a finite set
	- Denoted as $|S|$ for a finite set $S$ 
	- Sets inside sets only count as 1 element

**Set building notation:** provide a method for describing a wide range of sets (instead of expliclty listing them)
- **Requires:**
	- **Universe of discourse** ($U$): represents the existence of a large set encompassing any objects/elements that might be encountered
		- I.e. for divisibility → the universe is the set of integers $\mathbb Z$ 
	- An open sentence $P(x)$ such that $P$ is either true or false for each object $x$ in $U$ 
- **Set builder notation:** 
	- **Version 1:** $\{x\in U: P(x)\}$ 
		- Describes the set consisting of all objects $x$ such that $x$ is an element of $U$ and $P(x)$ is true
		- Can omit mention of universe → I.e. $\{x:P(x)\}$ 
		- *Example:* all even numbers → $\{x\in Z: 2|x\}$ 
	- **Version 2:** $\{f(x):x\in U\}$ 
		- Describes the set consisting of objects of the form $f(x)$ such that $x$ is an element of $U$ 
		- Introduces a function in place of an open sentence
		- *Example:* all even numbers → $\{2x: x\in Z\}$ 
	- **Version 3:** $\{f(x):x\in U, P(x)\}$ or $\{f(x):P(x), x\in U\}$ 
		- Describes the set consisting of all objects of the form $f(x)$ such that $x$ is an element of $U$ and $P(x)$ is true
		- Combines open sentence and function
		- *Example:* all positive integer powers of 5 → $\{5^{k}:k\in Z, k>0\}$ 
	- *Note* → for all of them:
		- Expression to left of colon gives typical element of the set
		- Expression to the right of the colon gives conditions that the variable must satisfy
			- Each comma = AND
	- *Note* → can use two variables
		- I.e. $\mathbb Q=\{\frac{a}{b}:a\in Z, b\in Z, b\neq 0\}$ 






# References

