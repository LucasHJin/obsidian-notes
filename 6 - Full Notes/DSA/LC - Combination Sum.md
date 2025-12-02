---
difficulty: medium
review:
---
2025-12-01 09:13

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(2^(t/m))
- Every call adds at least m to the running sum
- So it takes at most t/m calls → that’s the depth
	- Each time add/not → so 2^depth = 2^t/m 
**Space complexity:** O(t/m)
_______
# LC - Combination Sum

**Preliminary notes:** 
- *Note* → can have the same value an infinite number of times
	- All that matters is that the different combinations have different frequencies
- Each time you recurse
	- You want to start from the first value → go through the entire list
	- Add up and if it reaches the desired value → return
- Constraint part → just skip if the value is too big already

**Finished notes:** 
- *Note* → don’t need to call fxn after backtracking because that’s done naturally by moving onto the next value in the list
	- Calling it will make an infinite recursion
- Still need an index to track where you are (once you have moved past a certain value)
	- So that each combination is unique (not repeated)
	- I.e. 2, 3 is the same as 3, 2

# References

