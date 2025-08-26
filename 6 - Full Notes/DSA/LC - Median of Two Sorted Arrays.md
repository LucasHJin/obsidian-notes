---
difficulty: hard
review: true
---
2025-08-25 15:40

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(log(m+n))
**Space complexity:** O(1)
_______
# LC - Median of Two Sorted Arrays

**Preliminary notes:** 
- Use binary search + left/right pointers with modulo?
	- I.e. it’s `(l=0)%m` and `(r=m+n)%n` 
	- If `l>=m` or `r<m` → switch to only searching one array
	- WRONG ^^

**Finished notes:** 
- Logic:
	- Goal → split into 2 roughly equal partions (left and right) → then you have a middle
		- Key idea → WANT EVERY ELEMENT IN THE LEFT PARTITION TO BE SMALLER THAN RIGHT
	- Perform binary search on A and get remaining initial values from B
	- Then check if the last left element from A is ≤ first right element from B and vice versa
		- ![[Screenshot 2025-08-25 at 4.07.55 PM.png]] 
	- If this works → partition was done correctly
		- If even, take the smallest value from right partition and biggest value from left partition
		- If odd, just take smallest value from right partition (*NOTE* → ALWAYS KEEP RIGHT PARTITION GREATER OR EQUAL)
	- Else:
		- Shift left pointer `m+1` 
- *Note* → doing it without recursion is more efficient for space
	- How to handle edge cases
		- If `i or j > 0` then let it be -infinity
		- If `i+1 or j+1 > 0` then let it be infinity 
		- This allows us to make sure that if nothing is in A or B’s left or right halfs (when you reach edge), they won’t block it
			- Because `Aleft <= Bright` and `Bleft <= Aright` 

# References

