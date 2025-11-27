---
difficulty: easy
review:
---
2025-11-26 11:44

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn)
**Space complexity:** O(n)
_______
# LC - Last Stone Weight

**Preliminary notes:** 
- Relates to heaps again
- Use a max heap (heaviest are at the top) → negate values (or use heapify_max)
	- Pop twice → get y and x
	- If unequal values → take difference and push back into the heap
	- Repeat until length is 1
	- Return top value

**Finished notes:** 
- Do as above

# References

