---
difficulty: medium
review:
---
2025-08-24 10:20

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * logm)
**Space complexity:** O(1)
_______
# LC - Koko Eating Bananas

**Preliminary notes:** 
- Use binary search on the amount of bananas? 
	- Right bound is the max of the list → no point in going higher, doesn’t change anything
	- Left bound is min
	- Finishes in time `ceiling(pile/k)` 

**Finished notes:** 
- *Note* → check for `<=h` want the lowest value that works (don’t return early)
	- Return `l` in this case
- OR → each time it works, save it as the result
	- Then return it at the end

# References

