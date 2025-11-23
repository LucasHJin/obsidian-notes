---
difficulty: medium
review: true
---
2025-11-22 15:28

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Binary Tree Right Side View

**Preliminary notes:** 
- You can only see the rightmost given that it’s not blocked on the same height by more right
- Go down to the right
	- If the right doesn’t exist then go down left?
- Keep track of right most and next rightmost?
- Just split into left and right each time
- If right doesn’t exist → choose the left value (smaller value)

**Finished notes:** 
- Use BFS (it’s the last node in each layer)
	- After processing all layers → return the result
- BFS strategy is as detailed in [[LC - Binary Tree Level Order Traversal]] 

# References

