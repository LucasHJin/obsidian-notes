2024-08-05 14:25

Status:


Tags:
[[cp]]
[[cs]]
[[dp]]


___________________________________________________________________________
# Dynamic programming explained

**What is it?**
- A method of making an algorithm more efficient by storing some of the intermediate results
	- Helps with reducing repetitive computations → *optimization for plain recursion* 
	- Break down into smaller subproblems → ==write it recursively where the same function call + parameters happens multiple times and replace==
		- From exponential to polynomial time complexity

**Use cases:** 
- *Optimal substructure* → optimal results of subproblems solve overall optimal subresult
- *Overlapping subproblems* → same subproblem is solved multiple times in different parts of the problem

**Top down (memoization):** 
- Solution is still recursive → just add a table to keep track of solved subproblems
	- Before recursive call → check table for if already solved
	- After recursive call → store solution

**Bottom up (tabulation):** 
- Solution is iterative → build solution from smallest subproblem
	- Use dp table where it is initially filled with solutions for base cases and fill rest with recursive formula
	- *Note* → recursive formula only on table entries

![[Screenshot 2026-01-01 at 9.59.25 PM.png]]


**Example:** Fibonacci Sequence, finding the nth number
- 1, 1, 2, 3, 5, 8...
- **Step 1:** Come up with a recursive solution to the problem
```c++
int fib(int n) {
	//base case
	if (n==1 or n==2) {
		return 1;
	}
	result = fib(n-1)+fib(n+2);
	return result;
}
```
- This is inefficient because repeated calculations (i.e. fib(2))
- ![[Screenshot 2024-08-09 at 4.17.40 PM.png|400]]
	- $O(2^n)$
- **Step 2:** Store any repeated computations in recursion with **==memoization==** 
	- For memoization -> store calculated fib(n) to be used in the future
		- Using an array of len(n+1) -> store `fib(n) at [n]`
```c++
vector<int> memo(n+1, -1);

int fib(int n, vector<int> memo) {
	//if not empty
	if (!memo[n].empty()) {
		return memo[n];
	}
	//base case
	if (n==1 or n==2) {
		result = 1;
	} else {
		result = fib(n-1)+fib(n-2);
	}
	//if first time calculating
	memo[n] = result;
	return result;
}
```
- ==More efficient -> $O(n)$==
	- ![[Screenshot 2024-08-09 at 4.24.03 PM.png|400]]
- (Optional) **Step 3:** Create a bottom up approach (**Tabulation**)
	- Instead of building array recursively -> explicitly build it from **left to right** 
		- Iteratively solve subproblems and build up the solution from the smallest subproblems
```c++
vector<int> tab(n+1, -1);

int fib(int n) {
	if (n==1 or n==2) {
		return 1;
	}
	tab[1] = 1;
	tab[2] = 1;
	for (int i=3; i<=n; i++) {
		tab[i] = tab[i-1] + tab[i-2];
	}
	return tab[n];
}

```
- Also $O(n)$

**Common questions:**
- Knapsack problem
- Longest Common Subsequence
- Edit Distance

[[Prefix DP explained]] 
[[Interval DP explained]] 


# References

