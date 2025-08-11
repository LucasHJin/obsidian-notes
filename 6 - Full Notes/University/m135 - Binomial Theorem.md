2025-08-10 17:31

Status:


Tags:
[[uni]] 
[[m145]] 


_______
# m135 - Binomial Theorem

*Note:* Can be proved with [[m135 - Induction|induction]] 

**Useful:** 
- **Factorial:** repeated multiplication of adjacent integers starting from $1$ until $m$ 
	- $m!=\prod_{i=1}^{m}i$ 
- **Binomial coefficient:** is the combination of $m$ choose $n$ where $m\leq n$ and $m,n\in \mathbb Z^{+}$ 
	- $\binom{n}{m}=\frac{n!}{(n-m)!m!}$ 
		- Combination → order doesn’t matter
	- If $m>n$ → $\binom{n}{m}=0$ 
- **Pascal’s identity (PI):** For all positive integers $m, n$ with $m<n$:
	- $\binom{n}{m}=\binom{n-1}{m-1}+\binom{n-1}{m}$ 
	- Is a [[m135 - Summation, Product, Recurrence Notation|recurrence]] that allows you to calculate the value of binomial coefficient for all valid values
		- Allows you to produce the pascal’s triangle

**Binomial theorem:** 
- **Version 1:** For all integers $n\geq 0$ and all real numbers $x$,
	- $(1+x)^{n}=\sum\limits_{m=0}^{n}\binom{n}{m}x^{m}$ 
- **Version 2:** For all integers $n\geq 0$ and all real numbers $x$,
	- $(a+b)^{n}=\sum\limits_{m=0}^{n}\binom{n}{m}a^{n-m}b^{m}$  



# References

