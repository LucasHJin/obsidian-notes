2024-08-01 10:51

Status:


Tags:
[[school]]
[[math]]
[[calculus]]


___________________________________________________________________________
# DE exact solution - linear equations

In general:
- $nth$ order ordinary differential equation:
	- ${a_n}(x){y^{(n)}} + {a_{n - 1}}(x){y^{(n - 1)}} +  \cdots  + {a_1}(x)y' + {a_0}y - g(x) = 0$
	- ${a_n}(x)\dfrac{{{{\rm{d}}^n}y}}{{{\rm{d}}{x^n}}} + {a_{n - 1}}(x)\dfrac{{{{\rm{d}}^{n - 1}}y}}{{{\rm{d}}{x^{n - 1}}}} +  \cdots  + {a_1}(x)\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} + {a_0}y = g(x)$


**[[Differential equations|Linear equations:]]**
- A differential equation where:
	- The dependent variable and all of its derivatives are of first degree.
		- Dependent variable is often $y$
	- The coefficients of all terms with the dependent variable and derivatives depend only on the independent variable.
		- Independent variable generally $x$
- ==IB only focuses on first order linear equations of the form:==
	- ${a_1}(x)\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} + {a_0}y = g(x)$ 
	- $\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} + \dfrac{{{a_0}}}{{{a_1}(x)}}y = \dfrac{{g(x)}}{{{a_1}(x)}}$ 
	- $\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} + P(x)y = Q(x)$ ==<- most useful **standard form**==
		- Solved with integrating factor

**Steps:**
1. Write the equation in the form $y'+P(x)y=Q(x)$
	1. Identify $P(x)$ and $Q(x)$
2. Find $\int P(x)dx$
	1. Any antiderivative of $P$ (choose any $c$, typically $0$)
3. Find and simplify $I(x)=e^{\int P(x)dx}$
	1. **==Integrating Factor - $I(x)$==**
4. Multiply the equation by the integrating factor
	1. $I(x)y'(x) + I(x)P(x)y(x) = I(x)Q(x)$
5. Integrate both sides - Because $\frac{d}{dx}(I(x)y(x))=I(x)y'(x)+I(x)P(x)y(x)$ 
	1. $I(x)y(x) = \int {I(x)Q(x){\rm{d}}x}$
6. Solution is $y = \dfrac{{\int {I(x)Q(x){\rm{d}}x} }}{{I(x)}}$ 

**Example:**
- Step 1:
$y'-y=e^{x}$ 
$\Rightarrow P(x)=-1, Q(x)=e^x$ 

- Step 2:
$\int P(x)dx=\int -1dx =-x+c=-x$
	- You can do $c=0$ 

- Step 3:
$I(x)=e^{\int P(x)dx}=e^{-x}$

- Step 4:
$y'-y=e^x$
$e^{-x}y'-e^{-x}y=e^xe^{-x}$
$e^{-x}y'-e^{-x}y=1$

- Step 5:
$\int {e^{-x}y'-e^{-x}y}=e^{-x}y=\int 1=x+c$ 

- Step 6:
$\therefore y=\frac{x+c}{e^{-x}}=e^{x}x+e^{x}c$ 



![[Screenshot 2024-08-01 at 3.02.53 PM.png|300]]

# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/exact-solution-linear-equations-id-27278/
