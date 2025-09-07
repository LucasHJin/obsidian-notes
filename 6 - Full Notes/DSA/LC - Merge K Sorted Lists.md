---
difficulty: hard
review:
---
2025-09-07 13:05

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * k) / O(nlogk)
**Space complexity:** O(1) / O(logk)
_______
# LC - Merge K Sorted Lists

**Preliminary notes:** 
- Similar problem to [[LC - Merge Two Sorted Lists]] 
- Only ever consider 2 lists at a time
	- Use a [[Priority queue or Heaps explained|heap/priority queue]] where you always access the top 2 values for merging and then replace
		- Is O(n log k) + O(k) → faster but more space
	- OR → merge 2 lists → and then repeat with that merged list and a new list
		- Just the normal approach for this

**Finished notes:** 
- *Min heap approach:* 
	- Always take smallest node across all lists
		- Push head of non-empty lists to a heap
		- Pop smallest, attach to result list and add next node
	- `heappush` → auto keeps the heap property of having smallest on top
- *Divide and conquer approach:* 
	- Merge in parallel (like merge sort) → halve it each time
		- Still uses the exact same [[LC - Merge Two Sorted Lists]] appraoch
	- Use a new `mergedList` and then merge every 2 lists (skipping by 2)
		- Then update the list to new `mergedlist` and do this while the element amount is >1 
	- Best approach → O(logk) space

# References

