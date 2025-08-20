---
difficulty: medium
review:
---
2025-08-19 14:48

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Evaluate Reverse Polish Notation

**Preliminary notes:** 
- Use a stack
	- If it’s a digit → add it to the stack
	- If it’s an operator → use it on the two most recent values
		- Append that new value to the stack
		- Then continue
	- *Notes* → Can’t use integer division or just check for isdigit (both fail on edge case)

**Finished notes:** 
- First try!
	- Goes through once and then at most pops the last 2 values (O(1)) → so it’s O(n)

# References

