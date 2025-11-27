---
difficulty: medium
review:
---
2025-11-27 10:59

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogk)
**Space complexity:** O(k)
_______
# LC - Kth Largest Element in an Array

**Preliminary notes:** 
- *Note* → no sorting
	- Can I still use a heap? 
	- Min-heap + pop while length is greater than k
	- Need to use a new heap → can’t use heapify because that sorts it?
	- But this is O(nlogk) → worst case

**Finished notes:** 
- *Better solution for average time complexity*: O(n) average, O(n^2) worst case
	- Quick select (similar to quick sort)
		- Want to repeatedly split into halves
		- Randomly pick rightmost element as pivot each time
			- Go through elements and compare 
			- If less → put in array and shift, else just move on to the next element without inserting or shifting
			- Then the pointer indicates where the smaller and greater happens (left of)
			- Swap pointer with pivot
	- Go to the side of the partition where `length-k` index sits → that’s where it is
		- Repeatedly partition that side
		- If it equals the pointer → result is found (we know for sure that’s where the pointer element should reside)
	- *Note* → only recursing on one half of partition so more useful
	- *Note* → can do in place swaps to save memory (i.e. just swap the current pointer p with the value you are currently iterating through → because you’ll get to the value you swapped eventually)

# References

