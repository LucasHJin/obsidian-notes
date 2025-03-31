2024-08-01 10:51

Status:


Tags:
[[school]]
[[math]]
[[calculus]]


___________________________________________________________________________
# DE exact solution - separable equations

**Separable equations:**
- A first-order differential equation that can be written in the form $\frac{dy}{dx}=f(x)g(y)$
	- *Note that $\frac{dy}{dx}$ is better than $y'$ because you can cancel $dx$ in this case*
	- Essentially a differential equation where the expressions with $x$ and $y$ can be separated on opposite sides

**Steps:** 
1. **Separate the variables:** 
	1. $\dfrac{1}{{g(y)}}\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} = f(x)$
	2. BUT DON'T SEPARATE THE $\frac{dy}{dx}$ 
2. **Integrate** both sides with respect to x:
	1. $\int {\dfrac{1}{{g(y)}}\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}}{\rm{d}}x}  = \int {f(x){\rm{d}}x}$
	2. $\int {\dfrac{1}{{g(y)}}{\rm{d}}y}  = \int {f(x){\rm{d}}x}$
3. **Find the integrals for both sides**:
	1. Don't forget about $+C$
		1. $+C$ is only on 1 side (typically $x$ side)
	2. Will give an implicit equation for $y$
		1. (where $y$ isn't by itself just as $y$ on one side)
4. **(OPTIONAL) Express $y$ in terms of $x$**


**For Differential Equations:**
- **General solution:** The most general form of a solution to a system of equations without considering any initial conditions.
	- Involves an essential arbitrary constant
- **Particular solution:** The specific solution that satisfies some initial condition
	- Satisfies the condition of $y(x_0)=y_0$


**Example:** $y'=xy^2$ (can do it since it is separable)
- $\frac{y'}{y^2}=x$
- $\int \frac{1}{y^{2}}dy = \int x dx$
- $-\frac{1}{y}=\frac{x^2}{2}+c_1=\frac{x^2+2c_1}{2}$
- $y=-\frac{2}{x^2+2c_1}$
- $y=-\frac{2}{x^2+2c}$ -> ==Substituting for simpler constant==
	- Can substitute even if it's something like $A=e^c$ because is all constant







# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/exact-solution-separable-equations-id-27276/
https://www.khanacademy.org/math/ap-calculus-ab/ab-differential-equations-new/ab-7-6/e/separable-equations
