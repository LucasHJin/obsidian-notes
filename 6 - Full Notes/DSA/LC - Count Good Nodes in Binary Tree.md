---
difficulty: medium
review:
---
2025-11-22 16:15

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Count Good Nodes in Binary Tree

**Preliminary notes:** 
- Traverse tree and keep count of the max value seen before at each node
- If that value is greater than the current value → don’t add
	- Else you can add 1 to the count
- Traverse with [[DFS explained]] 
	- Can do this because no specified ordering

**Finished notes:** 
- As described
	- Can use global variables instead of a tail-recursive counting approach

# References

