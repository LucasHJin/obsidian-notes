2024-08-03 14:31

Status:
#in-progress


Tags:
[[math]]
[[school]]
[[calculus]]
[[BASE]]

___________________________________________________________________________
# Maclaurin Series Expansion

**What is it?**
- A special case of the [[Taylor series explained|Taylor series]] that uses the known point $x=0$ 
- Based on various [[Continuity theorems explained|continuity theorems]] 
- Can be used to:
	- Find approximations of complex functions
	- Investigate the [[Binomial series explained|binomial theorem]] from another angle
	- [[Evaluating limits with Maclaurin Series|Evaluate limits]] (indeterminate form of $\frac{0}{0}$)
	- [[Approximating definite integrals with Maclaurin Series|Approximate definite integrals]] 
	- [[Expanding a differential equation explained|Approximate solutions to differential equations.]] 
- Done with:
	- [[Expansions of special functions]] 
	- [[Error term explained]] 

## Maclaurin Series
- Is a simplified version of the Taylor series due to being centered at $x=0$ 
- Form:
	- $f(0) + (x)f'(0) + \dfrac{{{x^2}}}{{2!}}f''(0) + \dfrac{{{x^3}}}{{3!}}f'''(0) + ... = \sum\limits_{n = 0}^\infty  {\dfrac{{{f^{(n)}}(0)}}{{n!}}{x^n}}$ 
		- Removed all the $(x-a)$ 
- ==Generally, IB only quizzes Maclaurin==
**Example:** Find the first three terms of the Maclaurin series expansion of $f(x)=e^{e^x}$.
- Use the formula:
	- $\frac{f^{(0)}(0)}{0!}x^0=e$ 
	- $\frac{f^{(1)}(0)}{1!}x^1=\frac{e^{e^0}e^0}{1}x=xe$
	- $\frac{f^{(2)}(0)}{2!}x^2=\frac{(e^{e^0}e^0)e^0+e^{e^0}e^0}{2}x=x^2e$ 
- ![[Screenshot 2024-08-03 at 10.22.51 PM.png|300]]


_______
**Maclaurin Series Through Substitution:**
- Using substitution to manipulate a [[Expansions of special functions|known simple expansion]] to find a more complex expansion
- I.e. if you know the approximate Maclaurin Series expansion for $e^x$, you can use it to sub for $e^{x^2}$ 
	- Sub in $x^2$ for $x$ 
 $\qquad \because {{\rm{e}}^x} \approx 1 + x + \dfrac{{{x^2}}}{2} + \dfrac{{{x^3}}}{6} + \dfrac{{{x^4}}}{{24}}$ 
$\qquad \therefore {{\rm{e}}^{{x^2}}} \approx 1 + \left({{x^2}} \right) + \dfrac{{{{\left({{x^2}} \right)}^2}}}{{2!}} + \dfrac{{{{\left({{x^2}} \right)}^3}}}{{3!}} + \dfrac{{{{\left({{x^2}} \right)}^4}}}{{4!}} = 1 + {x^2} + \dfrac{{{x^4}}}{2} + \dfrac{{{x^6}}}{6} + \dfrac{{{x^8}}}{{24}}$ 
- ==Can be helpful to find first few terms==
- Note that if you are given it with $f(x)g(x)$ where $f(x)$ is solely in terms of $x$ and no the main priority:
	- You can put it on the outside and just move it in later (because it multiplies to every term of the other one no matter what)
	- I.e. ![[Screenshot 2024-08-05 at 8.36.14 PM.png]]

Can also try to manipulate the entire equation before substitution:
- ![[Screenshot 2024-08-04 at 10.29.45 AM.png]]



# References
https://tutorial.math.lamar.edu/ProblemsNS/CalcII/TaylorSeries.aspx 
