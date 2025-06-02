2024-08-01 10:51

Status:


Tags:
[[hs]]
[[math]]
[[calculus]]


___________________________________________________________________________
# DE exact solution - homogeneous equations

**Homogeneous equation:**
- A first-order differential equation is homogeneous if it can be written in the form $y'=F(\frac{y}{x})$ 
	- Equations of the form ${{p}_{n}}(x){{y}^{(n)}}+\cdots +{{p}_{1}}(x){{y}^{'}}+{{p}_{0}}(x)y=0$ are also technically homogeneous (==NOT IN SCOPE OF IB==)
	- Can check for homogeneous with:
		- $f(tx,ty) = {t^n}f(x,y)$

**Trick for solving:**
- Use the substitution $y=vx$
- Then, using product rule:
	- $\dfrac{{{\rm{d}}y}}{{{\rm{d}}x}} = \dfrac{{{\rm{d}}v}}{{{\rm{d}}x}}x + \dfrac{{{\rm{d}}x}}{{{\rm{d}}x}}v$
	- $y' = v'x + v$
- Can then rewrite the homogeneous equation:
	- $y' = F\left({\dfrac{y}{x}} \right) \Leftrightarrow v'x + v = F(v)$
		- This is [[DE exact solution - separable equations|separable]]
	- (could also sub $u=\frac{x}{y}$ but only doing 1 sub for simplicity)

**Steps:**
1. **Rearrange:**
	1. Into form $y'=F(\frac{y}{x})$ 
2. **Perform substitution:**
	1. $y=vx$ 
		1. $v=\frac{y}{x}$
	2. $y'=v'x+v$ 
3. Solve the resulting **[[DE exact solution - separable equations|separable equation]]**:
	1. $xv'+v=F(v)$
4. Replace $v$ with $\frac{y}{x}$
	1. Creates an implicit equation for $y$ -> rearrange for $y$ 

**Example:** $xy'=x+2y$
- Step 1:
$y'=1+\frac{2y}{x}$

- Step 2:
$v'x+v=1+2v$

- Step 3:
$v'x=1+v$
$\frac{v'}{1+v}=\frac{1}{x}$
$\int \frac{dv}{1+v}=\int \frac{dx}{x}$
$\ln|1+v|=\ln|x|+c$
$1+v=e^{\ln|x|+c}$
$1+v=e^{c}e^{\ln|x|}$
$1+v=\pm e^{c}x$ -> constant substitution
$1+v=Ax$
$v=Ax-1$

- Step 4:
$\frac{y}{x}=Ax-1$
$\therefore y=Ax^2-x$


# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/exact-solution-homogeneous-equations-id-27277/
