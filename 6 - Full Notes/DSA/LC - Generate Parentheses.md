---
difficulty: medium
review: true
---
2025-08-19 16:13

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(4^n / sqrt(n))
**Space complexity:** O(n)
_______
# LC - Generate Parentheses

**Preliminary notes:** 
- Could maybe use recursion to generate all the possible cases
	- I.e. for each recursive statement → check how many () there are and then either do first or second + backtrack
	- Have a counter for opening brackets and one for closing 
		- If they both match up to n → base case has been fulfilled
		- if opening < n → can have more
		- if closing < opening → valid to have a closing to close off the brackets

**Finished notes:** 
- Could use a list instead of string → reduces the memory consumption (join together at the end)
	- If using a list/stack → need to pop to backtrack afterwards
		- This is because lists share a mutable reference (not new one) so you need to undo to not affect other branches
		- But if you pass a copy → no problem
- Could also use [[Dynamic programming explained|DP]] 
	- NOTE → NOT NECESSARY
	- Relates to a very specific Catalan number formula (not well known)

# References

