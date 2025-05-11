2024-08-03 14:33

Status:


Tags:
[[math]]
[[hs]]
[[calculus]]


___________________________________________________________________________
# Taylor series explained

[[Taylor polynomials explained]]
- A Taylor polynomial can be used to approximate a function
	- Adding more terms makes the approximation more accurate
- What happens if you add terms to infinity ($n\rightarrow \infty$):
	- You get the **Taylor Series**

**Taylor Series:** A Taylor polynomial with terms added to infinity
- ${P_\infty }(x) = f(a) + (x - a)f'(a) + \dfrac{{{{(x - a)}^2}}}{{2!}}f''(a) + ...=\sum\limits_{n = 0}^\infty  {\dfrac{{{f^{(n)}}(a)}}{{n!}}{{(x - a)}^n}}$
	- Where $f$ is differentiable infinitely many times at $x=a$ -> this is the Taylor series centred at $x=a$ 
- When representing in **sigma notation:**
	- Can use !! for values that skip
		- Basically ! but for only same parity (i.e. ) 4! = ($2\cdot 4$)
		- I.e. $\frac{1}{2}\cdot \frac{3}{2}\cdot \frac{5}{2}\cdot =\frac{5!!}{2^n}$ 

**Example:** Find the Taylor series representing $f(x)=\ln x$ centred at $x=1$. 
- First try out some terms:
	- ${P}(x) = 0 + (x - 1) - \dfrac{{{{(x - 1)}^2}}}{2} + \dfrac{{{{(x - 1)}^3}}}{3} - \dfrac{{{{(x - 1)}^4}}}{4} +...$ 
- Then use sigma notation (or ... maybe)
	- $\sum\limits_{n = 1}^\infty  {\dfrac{{{{(- 1)}^{n + 1}}}}{n}{{(x - 1)}^n}}$ 

**NOTE:** If finding the taylor series of a polynomial:
- Will often end up with $0$ for further derivatives
	- Just manually calculate up until that point


# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/taylor-and-maclaurin-series-id-27285/
