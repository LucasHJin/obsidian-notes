---
difficulty: medium
review: true
---
2025-08-25 14:16

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(logn)
**Space complexity:** O(1)
_______
# LC - Search in Rotated Sorted Array

**Preliminary notes:** 
- Similar concept to [[LC - Find Minimum in Rotated Sorted Array]] 
	- Have a left and right pointer → find which segment the value is in
		- AKA → find pivot point
		-  If `m>=l` → left segment
			- Need to shift `l = m+1` to shift to the right segment
		- If `r>=m` → right segment
			- Shift `r=m` to find lowest of left segment
	- Then perform binary search within that segment
	- I.e. binary x2

**Finished notes:** 
- In general, here is how to find the pivot of any rotated sorted array:
	- If `nums[m]>nums[r]` (same as `m>=l`) → pivot must be to the right of `m` because it is greater than the biggest number in the right segment
	- Else if `nums[m]<=nums[r]` → pivot can be AT `m` or to the left of it → because maybe it’s the smallest value or maybe it’s second smallest
- **PIVOT:** SMALLEST ELEMENT

# References

