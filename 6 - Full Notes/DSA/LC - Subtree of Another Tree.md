---
difficulty: easy
review:
---
2025-11-20 11:17

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(m x n)
**Space complexity:** O(m + n)
_______
# LC - Subtree of Another Tree

**Preliminary notes:** 
- Perform checks like [[LC - Same Tree]] except only on the root

**Finished notes:** 
- Make a helper function that just checks if same tree
	- Iterate through tree until reach empty (False in this case)
		- Iterate with the subtree function
	- Return true if it works for any of them
- *Note* → make it a separate function to not redefine each loop

# References

