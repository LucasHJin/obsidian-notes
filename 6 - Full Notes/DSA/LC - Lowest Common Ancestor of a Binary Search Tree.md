---
difficulty: medium
review:
---
2025-11-21 14:12

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(h)
**Space complexity:** O(h)
_______
# LC - Lowest Common Ancestor of a Binary Search Tree

**Preliminary notes:** 
- Want the node above/equal to the given two nodes such that they are both children/grandchildren nodes of the node
- Iterate through the tree (log n height)
	- If the values are on opposite values of the current value → this is the lowest (going lower won’t capture both of them)
	- Else if one is equal → it’s equal to that
	- Else keep going down the side of the current node they are both on

**Finished notes:** 
- *Note* → can check that max is below or min is above for less checking cases

# References

