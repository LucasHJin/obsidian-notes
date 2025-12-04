---
difficulty: medium
review: true
---
2025-12-04 11:39

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * (2^n))
**Space complexity:** O(n)
_______
# LC - Subsets II

**Preliminary notes:** 
- Relates to [[LC - Subsets]] 
	- In this → no for loop (just use an index counter and iterate through list)
	- *Difference:* 
		- The array may contain duplicates (but you can’t have duplicate subsets)
- Use the index tracking again except also check if it has already been added
	- Sort array so that same values are next to each other
	- Skip element if same as previous one

**Finished notes:** 
- Same logic as [[LC - Combination Sum II]] 
	- Skip values at the same recursion level (not further though)
	- This way you never start recursion at the same level with the same value
		- I.e. can hit a 2 and then 2 in a later recursive call, but not start two of them with 2

# References

