2025-10-24 10:43

Status:


Tags:



_______
# cs145 - Midterm Help

**Stepping:**
- Will take 2 steps for lambda → substitute and then evaluate
	- And inner takes precedence

**Contracts:**
- Use most specific if possible (Int, Nat, etc.)
- If you can relate a parameter to another one → use generics
	- X → X means that the type stays the same as X
	- X can be a union of string types (multiple) → as long as it relates to the output (i.e. also produces an X)
- Last resort → use Any

**Abstract list functions:** 
- Exercise → write foldl, map, filter using only foldr
- They ALL evaluate in one step

**Transitivity:** 
1. if f is in O(g) and g is in O(h) then f is in O(h)
	1. We can find $N_{0}$ and $c_{0}>0$ such that for all $n≥N_{0}, f(n)<c_{0}g(n)$
	2. Similarly for $N_{1}$ and $c_{1}>0$, $g(n)<c_{1}h(n)$ 
	3. Pick $c=c_0\cdot c_1$ and $N=max(N_0, N_1)$ 
	4. So for $n\geq N$, $f(n)<c_0g(n)<c_0c_1h(n)=ch(n)$ 
2. Prove that $a^n$ is not in $O(b^n)$ for $a>b>1$ 
	1. Suppose for a contradiction that $a^n\in O(b^n)$ for $a>b>1$. We can find $N$ in natural numbers and $c>0$ such that $\forall n\geq N, a^n<b^n$.
	2. We want to find some $n_0\geq N$ such that $a^{n_{0}}\geq cb^{n_{0}}$ 
	3. $a^{n_{0}}\geq a^{\log_{a}c}\cdot a^{n_{0}\log_{a}b}=a^{n_{0}\log_{a}b+\log_{a}c}$ 
		1. … you can find $n_{0}>\frac{\log_{a}c}{1-\log_{a}b}$ and then reverse

**PRACTICE:** 
- 

# References

