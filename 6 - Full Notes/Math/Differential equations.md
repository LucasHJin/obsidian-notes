2024-07-31 14:05

Status:
#in-progress 

Tags:
[[hs]]
[[math]]
[[calculus]]
[[BASE]] 

___________________________________________________________________________
# Differential equations

## First order differential equations:
- The derivative $\frac{dx}{dy}$ of a function $y=f(x)$ is also a function → $f'(x)$
- **==Differential equation:==** An equation containing the derivatives of one or more dependent variable with respect to one or more independent variables.
	- Can be classified by type, order, linearity
	- **==Ordinary differential equation:==** An equation containing only ordinary derivatives of one or more dependent variable with respect to a single independent variable.
		- Functions with 1 independent variable and ordinary derivatives
		- Can still have multiple variables -> just all dependent on 1 (variable on bottom of derivative)
			- I.e. $\frac{dy}{dx}=2xy$
				- $y$ is dependent
				- $x$ is independent (denominator of derivative)
		- ==General form:==
			- $\frac{dy}{dx}=f(x,y)$ where $f(x,y)$ is a given function that specifies how the derivative depends on $x$ and $y$
	- **==Partial differential equation:==** An equation containing unknown multivariable functions and their partial derivatives. ==**(NOT FOR IB)**==
		- Multivariable equations with their partial derivatives
		- I.e. for $f(x,y) = {x^2}y + 2y$ → can find partial derivatives by treating other variables as constant
			- $\frac{\delta f}{\delta x}=2xy$
			- $\frac{\delta f}{\delta y}=x^2+2$
- **==Order of a differential equation:==** The highest order derivative in the equation. (like highest power in a polynomial) (**==ONLY 1st FOR IB==**)
	- First order:
		- $\frac{dy}{dx}+2y=e^x$
	- Second order:
		- $\frac{d^2y}{dx^2}+\frac{dy}{dx}=5y+x$
- **==Classifying by linearity:==** Linear vs Non-linear
	- A differential equation is said to be linear if all of the terms with dependent variables (including its derivatives) are first-order. (raised to power of 1)
		- Can't multiply $\frac{dy}{dx}\cdot y$ either → coefficients are dependent on $x$
	- First order linear ODE:
		- $y + 4x\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} = x$
	- First order non-linear ODE:
		- $(1 - y)\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} + 2y = \sin x$
		- $y^2+\frac{dy}{dx}=x$
		- $\frac{dy}{dx}+\cos{y}=x$
			- Because $\cos{y}$ is a trig function and not a 1st order polynomial

## Graphical Illustrations of ODEs ==(NOT PART OF IB)==
- [[Slope fields explained]]
- [[Isoclines explained]]

**Solving**:
- [[DE numerical solution - Euler's method|Numerical approximations of first-order differential equations using Euler’s method.]] 
- [[DE exact solution - separable equations|Exact solutions of separable differential equations using separation of variables.]] 
- [[DE exact solution - homogeneous equations|Exact solutions of homogeneous differential equations using substitution.]] 
- [[DE exact solution - linear equations|Exact solutions of first-order linear differential equations using an integrating factor.]] 

**PRACTICE:**
- https://math.libretexts.org/Bookshelves/Differential_Equations/Differential_Equations_for_Engineers_(Lebl)/1%3A_First_order_ODEs/1.E%3A_First_order_ODEs_(Exercises)
- 

**Use cases:**
- Newton’s law of cooling
- Half-life
- Exponential growth
- Logistic model
	- Models a population growth of the form $\frac{dP}{dt}=kP(a-P)$ 



# References

