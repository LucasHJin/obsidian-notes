---
difficulty: medium
review: true
---
2025-08-18 11:41

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(1)
**Space complexity:** O(n)
_______
# LC - Min Stack

**Preliminary notes:** 
- Implement as 2 lists → one for normal stack and one for min stack
- Most of it is just normal `pop` and `append`
- For pushing:
	- Need to check if its a new min value to be able to push it
- For popping:
	- Need to check if its the min value to pop it off
- ^ BETTER THAN USING MIN_VAL (O(n))

**Finished notes:** 
- Note → could technically do it with 1 stack
	- Don’t store actual values → store difference between current value and current minimum
	- If negative difference → means new minimum

# References

