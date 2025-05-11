2024-08-04 10:42

Status:


Tags:
[[math]]
[[calculus]]
[[hs]]


___________________________________________________________________________
# Binomial series explained

Related to the [[Binomial theorem explained|binomial expansion]] 
- $(a+b)^n$ expansion

**Maclaurin series expansion of $f(x)=(1+x)^p$** 
- $f(x) = {(1 + x)^p} = 1 + px + \dfrac{{p(p - 1)}}{{2!}}{x^2} + \dfrac{{p(p - 1)(p - 2)}}{{3!}}{x^3} + \cdots= \sum\limits_{n = 0}^\infty  {\left({\begin{array}{*{20}{c}} p\\ n \end{array}} \right){x^n}}$ 
	- If $p=n$ is a positive integer:
		- $0$ coefficients after the $x^n$ term
		- (The $n(n-1)(n-2)...$ product will always have a $0$)
		- So, you will get the finite expansion of $(1+x)^n$ 
	- If $p=n$ is not a positive integer:
		- The series is infinite
		- For $-1<x\leq 1$ this infinite sum equals $(1+x)^p$ 
			- ==It can be used for approximation for $-1<x\leq 1$ ==
- To note:
	- Generalized binomial coefficient:
		- $\left({\begin{array}{*{20}{c}} p\\ n \end{array}} \right) \equiv \dfrac{{p(p - 1)(p - 2) \cdots (p - n + 1)}}{{n!}}$ 
			- For $p-n+1$, it doesn't exist for the first 2 terms
				- Always going to be $1$ and $p$...
- This can be useful for generating approximations for irrational numbers
	- I.e. $e, \sqrt{2}, \pi,$ etc.

**Example:** Using the first three terms of the Maclaurin expansion of $\sqrt{1+x}$, find a rational approximation of $\sqrt{2}$.
- Since $f(x) = {(1 + x)^p} = 1 + px + \dfrac{{p(p - 1)}}{{2!}}{x^2} +  \cdots$
	- Then you know that:
		- $f(x)=(1+x)^{\frac{1}{2}}=1+\frac{1}{2}x+\frac{\frac{1}{2}\frac{-1}{2}}{2!}x^2+...=1+\frac{1}{2}x-\frac{1}{8}x^2+...$ 
- $\sqrt{2} = \sqrt{1+1} = 1+\frac{1}{2}-\frac{1}{8}+...=1.375$ 
- ![[Screenshot 2024-08-04 at 11.09.35 AM.png]]


# References

