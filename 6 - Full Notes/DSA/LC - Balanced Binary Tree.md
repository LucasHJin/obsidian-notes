---
difficulty: easy
review:
---
2025-11-19 14:47

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Balanced Binary Tree

**Preliminary notes:** 
- Get height of subtrees
	- Compare at each stage if leaf reached return true, else return false if the heights are not balanced
	- Else go to compare bottom 2

**Finished notes:** 
- Use [[DFS explained|DFS]] and keep track of a list with `balanced, height` 
	- Basically just the above solution but you eliminate repeated work by iterating once instead of twice

# References

