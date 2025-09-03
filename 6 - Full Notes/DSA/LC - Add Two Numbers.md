---
difficulty: medium
review:
---
2025-09-02 19:35

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(m+n)
**Space complexity:** O(1)
_______
# LC - Add Two Numbers

**Preliminary notes:** 
- Edge case → starts with 0, then just return the other one
- Keep track of overflow using a temp variable and store the values in nodes
- Iterate until both reach None
	- If either is None → add a 0 instead
	- If left with a carry → add on an extra node

**Finished notes:** 
- *Note* → need to use a dummy again
	- Allows it to add subsequent nodes

# References

