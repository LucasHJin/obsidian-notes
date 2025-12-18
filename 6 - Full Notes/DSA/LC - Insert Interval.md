---
difficulty: medium
review:
---
2025-12-17 16:11

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Insert Interval

**Preliminary notes:** 
- Relates to [[Intervals explained]] 
- Find position you can place the interval in based on the start of the interval
	- Then check the immediate before + after
- If before ends after → merge it
- If after starts before → merge it

**Finished notes:** 
- *Note* → to find the position in the interval list, you *can* use binary search
- Strategy:
	- Make a new list and append all intervals whose end is before the new start
	- Then you construct the `newInterval` by updating its values while it’s end is bigger than the start (and also within list size)
		- Start = min, end = max
	- Then add the rest

# References

