---
difficulty: medium
review: true
---
2025-12-23 11:52

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Maximum Subarray

**Preliminary notes:** 
- Have a max counter at all times
- Brute force → go through all sizes and calculate max subarray
- Use prefix sum?
	- Calculate the sum for each value
	- To find answer → find the max of the bigger index - smaller index

**Finished notes:** 
- Kadane’s algorithm → if the current sum becomes negative, it will always hinder future sums
	- I.e. -1+2 vs just 2 → just 2 is always going to be bigger
	- So if curr sum < 0 → reset
	- Keep track of current sum and overall max sum
- 

# References

