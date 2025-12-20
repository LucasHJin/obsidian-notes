---
difficulty: medium
review: true
---
2025-12-19 15:09

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn)
**Space complexity:** O(n)
_______
# LC - Non-overlapping Intervals

**Preliminary notes:** 
- Maybe?
	- While there is an overlap
		- Keep tracking until there isn’t one anymore
		- It’s the length of that - 2
	- Then continue?
- Remember → need to sort by start of intervals
	- Also note that if equal → then it’s not overlapping

**Finished notes:** 
- *Note* → use a greedy algorithm
	- Want to remove the interval that ends later if there is an overlap (that way, there is more space between intervals and less likely of another overlap)
	- So choose the min between the two end intervals if there is an overlap (represents the actual end → so we can check to see if it still overlaps or not even if we remove the later one)
		- Every time it’s overlapping → just increment counter 

# References

