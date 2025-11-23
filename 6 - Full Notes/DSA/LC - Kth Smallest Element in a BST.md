---
difficulty: medium
review: true
---
2025-11-23 13:39

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Kth Smallest Element in a BST

**Preliminary notes:** 
- Maybe?
	- Iterate through it as a BFS search row by row
	- Then go in reverse 
	- DOES NOT WORK
- Perform [[In order tree traversal|in-order]] traveral (left, node, right)
	- Get kth value from this traversal
	- Works because the rightmost of a child will be smaller than upper grandparent values

**Finished notes:** 
- *Note* → can store in memory with a global array but wastes memory
	- Instead just keep a counter
	- Subtract before checking the current node (because it’s 1-indexed)
		- If it equals 0 → it’s the answer
		- Replaces the appending

# References

