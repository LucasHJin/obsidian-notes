---
difficulty: medium
review: true
---
2025-12-08 19:27

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * (2^n))
- 2^n possible partitions (each step → either end current partition or continue it)
**Space complexity:** O(n)
_______
# LC - Palindrome Partitioning

**Preliminary notes:** 
- Want to return a list of all the possible ways you could split up the string into individual substrings such that each individual substring is a palindrome
	- To note → the split substrings need to be adjacent
- Can maybe go through individually, each time if it’s not the same value → keep adding until you reach the same value
	- If no same value reached → failed case
	- Else if same value reached → start case?

**Finished notes:** 
- Use 2 pointers → track current idx and start of current substring
	- Each step → either skip or partition on this current index
		- If so → check the index for if it is a palindrome
- OR → more standard version (use one single pointer)
	- Use 1 pointer keeping track of start
	- For each start idx → try all possible ending idx and only proceed with the recursion if the current one is a palindrome
		- I.e. `ab` won’t work so for loop will then try `aba` and since this is a palindrome it can make the first cut here and then repeat recursion on the rest
	- Backtrack is undoing the cut
	- First version is like this except it uses recursion to move the indexes forward

# References

