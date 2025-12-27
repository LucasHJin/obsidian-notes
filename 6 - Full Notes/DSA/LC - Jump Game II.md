---
difficulty: medium
review: true
---
2025-12-26 15:04

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Jump Game II

**Preliminary notes:** 
- Builds off of [[LC - Jump Game]] 
	- Difference → want the number of jumps to reach the end (it’s guarenteed to be possible)
		- Not just if you can reach the end
- Notes:
	- Can’t just choose the largest value each time
		- There might be an even larger value right after
	- Maybe go backwards still?
		- Keep track of an array of all successes so far
		- If you reach a new value which reaches a previous value in the array
			- Then reset to that checkpoint basically?

**Finished notes:** 
- Use left and right pointers
	- Iterate through range and find farthest reachable index from current index
	- Update right to the new index, left to right + 1 (guarantees must progress)
	- Like BFS where you traverse layer by layer
		- Going to one window of indexes each step (all reachable in that many steps by at least 1 path)
	- Keep on updating until right index reaches at least the end (or past it)

# References

