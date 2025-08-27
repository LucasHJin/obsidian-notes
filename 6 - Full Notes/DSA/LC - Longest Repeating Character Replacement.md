---
difficulty: medium
review: true
---
2025-08-26 12:12

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(m)
_______
# LC - Longest Repeating Character Replacement

**Preliminary notes:** 
- Use a dictionary and sliding window
- Want to replace the most frequent values
	- Use a dynamic sliding window where if it gets greater than `k` replacements then shrink the window

**Finished notes:** 
- Key note → Don’t need to actually replace
	- I.e. don’t need to keep track of which one is being replaced, all you need to know is that the number of replacements is equal to `window size - max frequency of a single character` 
- Note → max frequency is tracked over the entire array (always increases)
	- **Reason why you don’t have to decrement:**
		- Result is only going to be maximized as you find a new max frequency
		- Because if `max frequency` is higher then `length` can be higher as well
		- So you are never going to be able to get a higher result by decrementing → instead, you know that at least at 1 point in time, it was that value and so you were able to get `length = maxf + k` 

# References

