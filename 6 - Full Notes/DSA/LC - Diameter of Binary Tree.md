---
difficulty: easy
review:
---
2025-11-19 14:05

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Diameter of Binary Tree

**Preliminary notes:** 
- Return max of bottom tree and and 2 subtree heights 

**Finished notes:** 
- Perform [[DFS explained|DFS]] going to the bottom of the tree
	- Keep track of **diameter** as left+right and compare to previous ones
	- Return the **height** to previous function calls (so that it can use that in calculating new diameters)
- *NOTE* → need to mark `nonlocal d` to use it in dfs

# References

