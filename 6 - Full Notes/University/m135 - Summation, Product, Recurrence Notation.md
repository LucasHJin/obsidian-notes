2025-08-10 15:36

Status:


Tags:
[[cs]] 
[[m135]] 


_______
# m135 - Summation, Product, Recurrence Notation

**Summation:** For integers $k, m$ where $k\geq m$, “$\sum\limits_{i=m}^{k}x_{i}$” is equal to the repeated addition of values from $x_m$ to $x_k$ 
- *Index of summation* → $i$ (dummy variable used for incrementing)
- *Lower bound of summation* → $m$ 
- *Upper bound of summation* → $k$ 
- **Properties of summations:** 
	- It is linear (need same upper/lower bounds)
		- You can take the constant multiplication out of a summation
		- You can add/subtract 2 sums together as 1 
	- You can change the bounds → $\sum\limits_{i=m}^{k}x_{i}=\sum\limits_{i=m+r}^{k+r}x_{i-r}$ 
	- You can split into multiple sums by changing bounds → $\sum\limits_{i=m}^{k}x_{i}=\sum\limits_{i=m}^{r}x_{i}+\sum\limits_{i=r+1}^{k}x_{i}$ 
		- Useful for removing first/last term for **Principle of Mathematical Induction** 
		- I.e. ![[Screenshot 2025-08-10 at 3.43.31 PM.png]] 
**Product:** For integers $k, m$ where $k\geq m$, “$\prod_{i=m}^{k}x_{i}$” is equal to the repeated multiplication of values from $x_m$ to $x_k$ 
- All the variables represent the same as in summation

**Recurrence relation:** a sequence of values by giving one or more initial terms,
together with an equation expressing each subsequent term in terms of earlier ones
- Basically let $x_1$ be something and express $x_n$ based on $x_{n-1}$ 
- E.g. ![[Screenshot 2025-08-10 at 3.46.24 PM.png]] 
	- Allows you to define summations/products iteratively/recursively



# References
