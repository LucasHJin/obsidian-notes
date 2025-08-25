---
difficulty: medium
review: true
---
2025-08-24 10:45

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(logn)
**Space complexity:** O(1)
_______
# LC - Find Minimum in Rotated Sorted Array

**Preliminary notes:** 
- It still has a max in between the two boundaries somewhere
	- AKA → creates 2 sorted segments where min is the first element of the right segment
- Use binary search
	- Based on l, r, mid → at least 2 of them will be a part of one of the segments at any one time
		- If `m>=l` → left segment
			- Need to shift l = m+1 to shift to the right segment
		- If `r>=m` → right segment
			- Shift `r=m-1` to find lowest of left segment
		- If `num[l]<num[r]` → its already sorted
			- This is the case where the entire segment window is sorted → then its the smallest edge

**Finished notes:** 
- NOTE → This works because you compare the min between answer and the current midpoint at each step
	- So even if it moves on to process an invalid one afterwards → it already compared to the minimum then

# References

