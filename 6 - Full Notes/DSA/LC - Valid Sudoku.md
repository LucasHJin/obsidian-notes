---
difficulty: medium
review: true
---
2025-08-18 10:15

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n^2)
**Space complexity:** O(n^2) → or O(n)
_______
# LC - Valid Sudoku

**Preliminary notes:** 
- First thought → brute force through it
	- Check each row, each col, each subbox using a set
	- 1 pass through (n^2)
	- Use a hashmap filled with sets for each of the squares (index 0-8)
		- TO CALCULATE → $(row/3)*3+(col/3)$ 

**Finished notes:** 
- Could have also used a hashmap filled with sets for each row and col as well
	- IMPROVES MEMORY AND SPEED GREATLY → ~50% to ~90%
	- Because only need to do O(1) lookups instead of object creation and reallocating memory each time
- Could also use a tuple for the index
	- I.e. $(row/3,col/3)$ → also works but is simpler because its more self evident what it represents
- *Note* → could technically use a bitmask for improved memory

# References

