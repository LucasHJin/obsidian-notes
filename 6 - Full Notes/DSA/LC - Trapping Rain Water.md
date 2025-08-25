---
difficulty: hard
review: true
---
2025-08-23 15:38

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Trapping Rain Water

**Preliminary notes:** 
- Only has water when it goes in a dip → big, small big
	- Size depends on index between the bigs + the size of the smaller big
		- Minimum - the height at that index
**Finished notes:** 
- Prefix solution:
	- Go through the list twice (once from front, once from behind)
	- Get the max height (prefix/suffix max) for each index
		- Do this by getting max of prev and current
	- Then iterate and just use `min(prefix[i], suffix[i])-height[i]` 
- Two pointer solution (reduces space complexity to O(1))
	- Pointers start on two ends + keep track of max left and max right
	- Shift the one that contains the lower value (or either if same) (guarenteed we can calculate the amount of water trapped because we know that the right can’t be the height we use if the left bound is smaller)
		- Only add if `max - height[i]>0` 
		- Otherwise update max
		- *Don’t forget to shift the pointers* 

# References

