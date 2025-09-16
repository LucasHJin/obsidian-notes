2025-09-11 10:30

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Measuring Efficiency

*Note:* counting steps → approximating the total run time of the program
- Max number of opening parentheses = memory usage
- [[cs145 - Efficiency Examples]] 

**Helper functions:** Used to break down problems into smaller problems
- ALLOWED + ENCOURAGED
- *Usecases:* 
	- Make the program easier to read, understand, more efficient (avoid repeated calculations)
- **Parameterizing the variable:** mimic variables in Racket by using parameters in functions

**Tail recursion:** writing a function in such a way such that you never do anything with the recursive call
- **KEY IDEA:** the recursive call cannot be an argument of any computation
	- Calcs must happen before the recursive call
	- Can’t have some expression surrounding the subcall (used in subexpression)
- **KEY IDEA:** must have at least 1 accumulator that stores intermediate results
- Explanation:
	- Recursion → need to go inwards and the back out (>)
		- Memory increases (more parentheses)
	- Tail recursion → only go forwards
		- When you are done (iteration is at 0) → **return the accumulator** 
		- ==LENGTH STAYS THE SAME (FIXED AMOUNT OF MEMORY/PARENTHESES)== 
- [[cs145 - Tail Recursion Examples]]
	- **NOTE:** if you have a repeated calculations, use a helper to avoid repeating that calculation of the same expression


**Example helper:** 
- Original Fib –> [[cs145 - Efficiency Examples]] 
- New:
	- Use a recurrence relationship instead
	- `fib(n) = fib(n-1) + fib(n-2)` 
		- Save these values in parameters for fast computation
![[Screenshot 2025-09-11 at 11.19.40 AM.png]] 
- Just iterates forward 

| N   | (fib N) | (fib-steps N) |
| --- | ------- | ------------- |
| 0   | 0       |               |
| 1   | 1       |               |
| 2   | 1       |               |
| 3   | 2       |               |
| 4   | 3       |               |
| 5   | 5       |               |
| 6   | 8       |               |
| 7   | 13      |               |



# References

