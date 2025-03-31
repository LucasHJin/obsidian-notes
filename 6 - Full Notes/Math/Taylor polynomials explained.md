2024-08-03 20:00

Status:


Tags:
[[math]]
[[school]]
[[calculus]]


___________________________________________________________________________
# Taylor polynomials explained

An approximation technique to approximate complex functions with simpler functions (ie. polynomials)
- Because easy to integrate/differentiate
- Basically, based on a chosen $a$ value, it will replicate the function $f(x)$ locally at $a$ so you can plug in numbers and get similar results
	- I.e. plug in $x=1$ into $P_k(x)$ 

*NOTE:* Approximations are only useful if you can estimate the error that you would get from using it instead of the actual value
- [[Error term explained]]

**Taylor polynomial, $P_k(x)$**: a polynomial of degree $n$ used for approximating $f(x)$ with the approximation at $a$ 
==In math:==
$\qquad\begin{align}{P_k}(x) &= f(a) + (x - a)f'(a) + \dfrac{{{{(x - a)}^2}}}{{2!}}f''(a) + ... + \dfrac{{{{(x - a)}^k}}}{{k!}}{f^{(k)}}(a) \\&= \sum\limits_{n = 0}^k {\dfrac{{{f^{(n)}}(a)}}{{n!}}{{(x - a)}^n}} \end{align}$
- **To note:**
	- These $^{(n)}$ denote higher order derivatives
	- A Taylor polynomial of degree $k$ has $k+1$ terms 
		- No derivative, 1 derivative... k derivative
	- For $a$:
		- Choose an $a$ near the area of interest!!
			- Loses accuracy as the Taylor polynomial gets further from $a$ 
		- ==IN IB -> ONLY $a=0$==

**Example:**
Approximate $f(x)=\ln x$ with a sixth-order Taylor polynomial centred at $x=1$. Use your polynomial to find an estimate of the value of $\ln 0.4$.
- $P_{k}x = f(1)+(x-1)f'(1)+...+\frac{(x-1)^6}{6!}f^{(6)}(1)$ 
![[Screenshot 2024-08-03 at 9.24.56 PM.png]]
![[Screenshot 2024-08-03 at 9.27.05 PM.png|300]] Approximates similarly when close to 1


# References

