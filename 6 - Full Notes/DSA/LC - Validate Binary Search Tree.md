---
difficulty: medium
review: true
---
2025-11-23 13:22

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Validate Binary Search Tree

**Preliminary notes:** 
- Relates to [[cs145 - Specific Trees]] 
- Can’t just track current bound
	- I.e. it for a LR path it might go 5 3 6 but it doesn’t work then
- On left side → upper bound = prev node, no lower bound
- On right side → lower bound = prev node, no upper bound

**Finished notes:** 
- Traverse using a single function [[DFS explained|DFS]] → track lower and upper bounds (starting from `infinity`, `-infinity`)
	- `float("inf"), -float("inf")`

# References

