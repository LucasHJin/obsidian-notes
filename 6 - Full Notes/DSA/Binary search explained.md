2025-08-16 16:04

Status:


Tags:
[[lc]] 
[[dsa]] 


_______
# Binary search explained

General idea → cut problem in half at every step until answer is reached

**How it works:** set 2 pointers (starting at start and end of sorted array)
- As long as they haven’t crossed each other → keep checking if value is found or if not → based on some condition, move the pointers

**Actual use cases:** 
- YOU DON’T ALWAYS NEED A SORTED ARRAY → **just a monotonic condition** 
	- I.e. it only changes in one direction (can stay the same but won’t go in opposite direction)
	- I.e. if something is always false until it turns true → then it’s monotonic [F, F, F, T, T] 
- **Problem use cases:** no sorted array but you want to minimize/maximize something
	- ![[Screenshot 2025-08-16 at 4.10.27 PM.png]] 

**Example:** 
- First true in a sorted boolean array → has one directional property
	- If value at the index is true → could be answer (update temp boundary) and then move to the left
	- If invalid → shift to the right
	- Continue until overlaps
- Find minimum in a rotated sorted array → I.e. some values move to the front
	- Can divide the array → all numbers greater than the last element vs all numbers smaller
	- Compare each value to the last number in the array (if smaller then true) → find the first true


# References

