---
difficulty: medium
review: true
---
2025-08-17 11:46

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n) → NO DIVISION OPERATOR
**Space complexity:** O(n) → can be changed to O(1) not including output array
_______
# LC - Product of Array Except Self

**Preliminary notes:** 
- First thought → nested loop to get each of the n values
- Second thought → calculate product of all and then go through once and just divide by the value 
	- Can’t do this → no division operator allowed
- Third thought → make something like a prefix sum array + a suffix sum array excluding the values at each index
	- Go both ways
	- (x, y, z) → (1, x, xy) AND (zy, z, 1)
		- Multiply to get desired result

**Finished notes:** 
- How to make the [[Prefix sum explained|prefix/suffix sum]] more optimal:
	- Compute the prefix through first pass and then store in the output
	- Then compute suffix and multiply by prefix in output in real time

# References

