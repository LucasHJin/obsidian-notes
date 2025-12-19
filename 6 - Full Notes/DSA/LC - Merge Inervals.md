---
difficulty: medium
review:
---
2025-12-18 11:41

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn)
**Space complexity:** O(n)
_______
# LC - Merge Inervals

**Preliminary notes:** 
- Go by adjacents
	- Keep track of current start and end
	- Keep updating them until the current end is earlier than current start and then restart it
		- When updating → it’s not always the new value
		- Should just be the max of the 2 ends
- Also need to sort at the start + have an append at the end for last case not appended

**Finished notes:** 
- 

# References

