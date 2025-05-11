2024-08-12 23:15

Status:


Tags:
[[math]]
[[statistics]]
[[hs]]


___________________________________________________________________________
# Linear regression continued explained

**Recap:**
- Linked to:
	- [[Correlation strength explained]] 
	- [[Linear correlation explained]] 
- Given the **least squares regression line** where $y=ax+b$
	- $y$ is dependent on $x$ 
		- You can predict $y$ from $x$ but NOT the other way around


**Residuals**: The vertical distance between each data point and a least-squares regression line
- (difference between predicted $y$ value and measured $y$ value)
- To find least squares regression line, minimize all these residuals 
	- (squared to eliminate negatives)
- ![[Screenshot 2024-08-13 at 9.17.31 AM.png|400]] 

**How to predict x from y:**
- **BAD WAY:**
	- $x=\frac{y}{a}-\frac{b}{a}$ 
		- You are treating $y$ as independent and $x$ as dependent
		- The residuals are now horizontal and there is no logical causation![[Screenshot 2024-08-13 at 9.26.39 AM.png|300]] 
- **GOOD WAY:**
	- $x=c+dy$ 
		- Alternate form of the least-squares regression equation
		- Makes the $y$ the independent variable + keeps residuals vertical
	- For the calculator, just plug in the $x$ and $y$ values swapped
		- And then just interpret the other way
	- IMPORTANT:
		- Confirm that the value of 𝑥 could logically be dependent on the value of 𝑦.
		- Use the same calculator function, but reverse the data you enter for 𝑥 and 𝑦.
		- Reversing the variables does not change 𝑟.



# References

