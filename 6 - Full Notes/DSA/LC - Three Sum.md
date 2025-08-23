---
difficulty: medium
review: true
---
2025-08-21 22:33

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n^2)
**Space complexity:** O(n)
_______
# LC - Three Sum

**Preliminary notes:** 
- Can’t use 3 pointers → don’t know how to move
- Could fix 1 value → and then run a 2 pointer for that (sorted)
	- But don’t want to be redundant with checks
	- Make sure the first value (i) is always different
	- Only run to the right of the first index → i.e. guarenteed nothing on left because its sorted so it was already checked (no duplicates)

**Finished notes:** 
- Need to change either the j or k index after the answer is found
	- Keep on changing it until the values are different (no duplicates)
- CAN ALSO DO AN INITIAL CHECK FOR `nums[i]>0` 
	- Because 3 positive never equals 0
- Could also do it with a hashmap

# References

