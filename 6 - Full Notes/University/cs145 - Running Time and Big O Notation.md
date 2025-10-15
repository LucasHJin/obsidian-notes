2025-10-09 10:05

Status:


Tags:
[[cs]] 
[[uni]] 
[[cs145]] 


_______
# cs145 - Running Time and Big O Notation

**Abstracting running time:** 
- Bad use cases:
	- Steps → tedious (too granular)
	- Time → specific to a specific machine + need to have multiple inputs
- **Asymptotic runtime:** i.e. what asymptote does it approach over the long run (polynomial, log, etc.)
	- Constants don’t matter (multiplied and added)

**Big O Notation:** $O(f(n))$ is the set of all functions $g(n)$ which have asymptotic runtime $g(n)\leq c\cdot f(n)$ (there exists a $c>0$ and $n_0>0$ such that if $n\geq n_0$ then the above is true)
- *Note* → $O(f(n))$ is a set so it’s not equal to $g(n)$ 
- **Lemmas:** 
	- Multiplying/adding to $g(n)$ doesn’t matter
	- If $a$ is a set in $O(f)$ and $b$ a set in $O(g)$:
		- $a+b \text{ in } O(f) \text{ if } O(g) \subset O(f)$  
		- $a+b \text{ in } O(g) \text{ if } O(f) \subset O(g)$  
		- $a+b \text{ in } O(f)=O(g) \text{ if } O(f)=O(g)$  
- **Big O Classes:** So
	- Constant
	- Logarithmic
	- Square root
	- Linear
	- Linearithmic ($O(nlogn)$) 
	- Quadratic
	- Cubic
	- Polynomial
	- Exponential (base 2) 
	- Exponential (base $b>1$) 
	- *NOTE:* 
		- $O(1)\subset O(n)\subset ...$ 
		- If $k<0$ then if $g(n)\in O(n^k)$ then $g(n)\in O(1)$ 
- **Monotonic:** running time increases as size increases
- *Notes:* 
	- Assume n is a positive integer (size of input)
	- $c$ doesn’t need to be an integer but $n_0$ should
- ![[Untitled_Artwork 11.png|300]] 

**Big O and [[m135 - Induction|Induction]]:** ![[Screenshot 2025-10-09 at 10.25.52 AM.png]]
- ^^ Fails when proved without definition
- **Proof:** Since $g(i)\in O(i)$, $\exists c>0, n_0>0$ such that $\forall n\geq n_0,g(i)\leq c\cdot i$ 
	- $\sum\limits_{i=1}^{n}g(i)\leq \sum\limits_{i=1}^{n}c\cdot i= c\sum\limits_{i=1}^{n}i=c\cdot \frac{n(n+1)}{2}=\frac{c\cdot n^{2}}{2}+\frac{c\cdot n}{2}\leq\frac{c^{*}\cdot n^{2}}{2}+\frac{c^{*}\cdot n^{2}}{2}=c^{*}n^{2}$ 
		- Pick $n_{0}^{*}=max(1,n_{0})$ and let $c^{*}=c$ → because then $n^{2}\geq n$ ALWAYS
- Problem with induction
	- When you assume $\sum\limits_{i=1}^{n}g(i)\in O(n)$ → $n$ is not constant (constants are being multiplied so not valid)

**Proof example:** Prove $10x^{2}+20\in O(x^{2})$ 
- Need to find a $c>0, n_0>0$ such that $\forall n\geq n_{0}, 10x^{2}+20\leq c\cdot x^2$ 
	- Pick $c=30, x_0=10$ 
	- $10x^{2}+20\leq 10x^{2}+20x^{2}=30x^{2}$ 
	- Therefore it has been proven
- *MORE EXERCISES* → PAGE 11 IN THE SLIDES

**Disproof example:** Prove $x^{2} \not\in O(x)$ (normally by contradiction)
- Need to show there does not exist any $c>0, x_{0}>0$ …
- Suppose there were $c>0, x_{0}>0$ such that $x^{2}\leq cx$ for all $x\geq x_0$ 
	- Pick $x=max(x_0,c+1)$ → $x\geq c+1$ 
	- $x\cdot x\geq (c+1)x$ 
	- $x^{2}\geq c\cdot x + x > cx$ 
	- This is a contradiction so $c,x_0$ can’t exist such that the conditions are satisfied

**Runtime of Elementary Racket Functions:** all have running time of $O(1)$ 
- Caveat → most arithmetic functions have more than constant time
- **Unit cost model:** make faster ones like `first, rest` take longer so that on average, arithmetic takes shorter time

**Runtime of Non-elementary Racket Functions:** process inputs in a different way
- `(reverse L)` → O(n) (n is length of L)
- `(append a b)` → O(n) (n is length of a)
- `(length L)`  → O(n) (n is length of L)
- `(member? e L)` → O(i) (e is ith element of L)
- `(list-ref L i)` → O(i) (to access ith element of the list)

**Runtime of BST functions:** 
- `bst-insert, bst-delete, bst-find` → O(h) where h is the bst-height of t
	- *Note* → h can be O(n)
- `avl-insert, avl-delete, avl-find` → O(log n)

**AVL trees:** 
- guarantee that the height of a tree is $O(\log n)$ 
	- Don’t guarantee minimal height → just height of subtrees differ by 1
- Note for $n$ nodes and $h$ height: $h\leq \log_{\varphi}(n+2)$ 
	- DONT HAVE TO UNDERSTAND UNTIL CS240

# References

