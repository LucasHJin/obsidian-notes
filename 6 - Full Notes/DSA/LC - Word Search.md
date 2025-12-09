---
difficulty: medium
review: true
---
2025-12-07 19:17

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(m * (4^n)) → m is number of cells
**Space complexity:** O(n)
_______
# LC - Word Search

**Preliminary notes:** 
- 4 directions → up, down, left, right
	- Can only go in that direction if it’s within the bounds of the board
	- Stop anytime the current letter does not match up
- Strategy:
	- Each backtracking has a loop of 4 directions
	- Use (x,y) to keep track of board position and index to keep track of current position in list
	- *Note* → can’t repeat same value (need to keep this in mind)
		- I.e. if it’s BCB, you can’t go B to C back to the same B
		- Use a separate grid of same size with true/false (all false at the start)
- Use DFS

**Finished notes:** 
- Stop recursion (return false) if not in bounds, not correct letter, already visited
- No need to keep track of the word itself (because you just return True/False)
- No need for a loop
	- Each layer of searching → try the 4 directions
		- Use an `or` → if any of them work, it’s good
	- ==The backtracking is unmark visited== 
	- If you do use a loop, you need to check outside of it
		- So that you check for the first value
- *Note* → could also use a hashset
- *NOTE* → for making lists, use list comprehension
	- DON’T USE `[False] * x` → only for 1D lists
		- Or else every row same list in memory

# References

