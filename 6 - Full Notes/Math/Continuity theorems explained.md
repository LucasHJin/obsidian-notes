2024-08-03 14:34

Status:


Tags:



___________________________________________________________________________
# Continuity theorems explained ==(NOT PART OF IB EXAMS)==

**==Definitions:==**
- **Continuity:** A point is continuous if $\mathop {\lim }\limits_{x \to c} f(x) = f(c)$. 
	- An interval is continuous if it is continuous at each interior point within the interval.
		- (Basically no breaks, jumps or gaps in line)
	- Conditions:
		- $f(c)$ is defined in the range of $f$ 
		- $\mathop {\lim }\limits_{x \to c} f(x)$ exists
		- $\mathop {\lim }\limits_{x \to c} f(x) = f(c)$ 
	
- **Differentiability:** a function is differentiable if it is *smooth* enough that it approaches linearity when zooming in
	- Conditions for a point:
		- Must be ==continuous== at the point
		- Must have ==local linearity== at the point
	- Conditions for a function:
		- Differentiable at every point in the domain
	- *Any of the following makes it not differentiable:*
		- Cusp or Corner (sharp turn)
		- Discontinuity (jump, point, or infinite)
		- Vertical Tangent (undefined slope)


**Intermediate value theorem:**
- A continuous function won't ever take on 2 terms without taking on all the terms between them
	- I.e. there is no sudden jump, need to move from point A to point B
- ==In math:==
	- Let $f$ be a continuous function on $[a,b]$ where $f(a)\neq f(b)$
		- Then, for every $y_0$ where $a<y_o<b$, there is at least one ${x_0} \in (a,b)$ such that $f(x_{0})=y_0$ 
	- *Note that there can be multiple $x_i$'s where $f(x_i)=y_0$ if the graph goes up and down multiple times*
- ![[Screenshot 2024-08-03 at 5.45.14 PM.png|300]]


**Rolle's theorem:** 
- Is an expansion of the intermediate value theorem (but applied to slopes)
- A differentiable function that starts and stops at the same y-value must somewhere along the interval have a gradient of 0
	- Basically at the very top or bottom, $gradient = 0$
	- Or if its flat the entire way -> gradient is always 0
- ==In math:==
	- Given that the function $f$ is:
		- continuous on the closed interval $[a,b]$ 
		- differentiable on the open interval $(a,b)$ and
		- $f(a)=f(b)$ 
	- Then there is a value $c$ where $a<c<b$ such that $f'(c)=0$ 
- ![[Screenshot 2024-08-03 at 5.50.36 PM.png|300]]


**Mean value theorem:** 
- Is an expansion of Rolle's theorem to not be limited by start and end points needing to be the same value
- Somewhere along the segment of a differentiable function, there must be a point with a gradient equal to the gradient between the endpoints (average gradient)
	- Because to reach a certain gradient, average, must have above and below or all equal -> need to pass by the gradient at some point
- ==In math:==
	- Let $f$ be a function that is:
		- continuous on the closed interval $[a,b]$ and
		- differentiable on the open interval $(a,b)$ 
	- Then, there is a $c$ where $a<c<b$ such that $f'(c) = \dfrac{{f(b) - f(a)}}{{b - a}}$ 
- ![[Screenshot 2024-08-03 at 7.54.58 PM.png|300]]



# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/continuity-theorems-id-27282/
