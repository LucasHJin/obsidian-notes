---
difficulty: medium
review:
---
2025-08-19 17:11

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Daily Temperatures

**Preliminary notes:** 
- Make a maxheap using stack?
- Use a stack to maintain indices such that the smallest values are at the top?
	- Then iterate through the list in reverse
	- Each time you see a smaller value (for which current iterator is bigger), keep popping until you get to a value that’s larger than the temp at the current iterator
	- The difference between this is the amount of days you are waiting
		- Makes sense → want to wait until a day you already saw comes up that is hotter

**Finished notes:** 
- Can also iterate forwards → means you don’t have to do an O(n) reverse afterwards as well
	- Can also store indices + temperatures together → doesn’t really matter because O(1) lookup
	- How it works:
		- Keep a stack that tracks coldest days on top
		- When a warmer day is found → keep popping and updating these colder days until its no longer a warmer day 
		- Then, add this current warmer day to find its warmer day
		- If none found → 0

# References

