2024-07-31 20:46

Status:


Tags:
[[school]]
[[math]]
[[calculus]]

___________________________________________________________________________
# ODE numerical solution - Euler's method

**Requirements/Limitations:**
- Given a certain point
- Must be a first order differential derivative
- Provides approximation

**How?**
- Follows idea of [[Slope fields explained|Slope fields]] - draw a curve based on the known point and the slope for a set distance and repeat
	- Allows to  approximate the length travelled along the solution curve from a point
- General formulas:
	- $x_{k+1}=x_k+\Delta x$
	- ${y_{k + 1}} = {y_k} + F({x_k},{y_k}) \cdot \Delta x$ 
	- $F(x_{k,}y_k)=y_{n}+\Delta xy'_n$ 

**Example:** $y'=x-y^2$ where $y(1)=1.5$, use step size 1.0 to estimate $y(2)$
- Step size: $\Delta x=1$ -> only need 1 step
- New $x$ value:
	- ${x_1} = {x_0} + \Delta x = 1 + 1 = 2$
- New $y$ value:
	- $\dfrac{{\Delta y}}{{\Delta x}} \approx \dfrac{{dy}}{{dx}} = x - {y^2} = 1 - {1.5^2} =  - 1.25$
	- $\Delta y =  - 1.25\Delta x =  - 1.25(1) =  - 1.25$
	- ${y_1} = {y_0} + \Delta y = 1.5 - 1.25 = 0.25$
- Solution:
	- $(2, 0.25)$ 
	- ![[Screenshot 2024-08-01 at 11.06.37 AM.png|400]]

**==If you do smaller step sizes -> more steps -> more accurately following==**
- ![[Screenshot 2024-08-01 at 11.09.40 AM.png|400]] 
- Use the calculated values as the new values to plug in and repeat
	- Sort of like estimating an integral

**Can make a table:**

| $k$ | $x_k$ | $y_k$ | $y_k'=F(x,y)=\frac{\Delta y}{\Delta x}$ |
| --- | ----- | ----- | --------------------------------------- |
| 0   | 1     | 0.5   | 0.5                                     |
| ... | ...   | ...   | ...                                     |
Multiply $y_{k}'$ by $\Delta x$ and add to $y_k$ for $y_k+1$



# References

https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/numerical-solution-eulers-method-id-27275/