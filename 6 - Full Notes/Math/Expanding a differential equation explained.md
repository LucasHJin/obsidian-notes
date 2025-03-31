2024-08-04 15:06

Status:


Tags:
[[math]]
[[school]]
[[calculus]]


___________________________________________________________________________
# Expanding a differential equation explained

- Provides another numerical method for approximating a [[Differential equations|differential function]] 

**How?**
- When given a ==first order differential equation== and a starting point ==(x, y)==:
	- You can use the starting point and the evaluation of all of the necessary derivatives to approximate a solution
	- More terms = more accurate
- In simple terms:
	- Find first $n$ terms of Maclaurin series for a function (or taylor series if not given 0 for the starting $x$ coordinate)
		- Do this by calculating the derivatives of $y'$ and substituting in
		- NOTE: the base $y$ will often be provided with coordinates
	- Then plug in $x$ value for approximation

**Example:** A solution curve of the differential equation $y'=x-y^2$ passes through the point $(0,1)$. Find the first four terms of the Maclaurin series corresponding to this solution. Hence, using these terms, find an approximate value of $y(1)$.
- In this case, $y(x)$ is $f(x)$ 
	- So we want $y, y'', y'''$ with $x=0$ plugged in-> we already have $y'$ 
	- $y(0)=1$ given
	- $y'=x-y^2$
		- $y'(0)=-1$
	- $y''=(y')'=(x-y^2)'=1-2yy'$ 
		- $y''(0)=1-2(1)(-1)=-3$
	- $y'''=(y'')'=(1-2yy')'=-2y'y'-2yy''$ 
		- $y'''(0)=-2(-1)(-1)-2(1)(3)=8$ 
- Then based on the Maclaurin series:
	- $y(x) \approx y(0) + y'(0)x + \dfrac{{y''(0)}}{2}{x^2} + \dfrac{{{y^3}(0)}}{6}{x^3} = 1 - x + \dfrac{3}{2}{x^2} - \dfrac{8}{6}{x^3}$ 
- So the approximation is:
	- $y(1) \approx 1 - (1) + \dfrac{3}{2}{(1)^2} - \dfrac{8}{6}{(1)^3} = \dfrac{1}{6}$ 


# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/expansion-from-a-differential-equation-id-27289/
