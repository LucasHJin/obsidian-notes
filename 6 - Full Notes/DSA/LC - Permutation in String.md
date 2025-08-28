---
difficulty: medium
review: true
---
2025-08-27 15:16

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Permutation in String

**Preliminary notes:** 
- Use 2 sets and check if in it?
	- Need same frequencies → like [[LC - Valid Anagram]] 
	- Or a dictionary → as long as its the same, can continue
- Fixed window size of `len(s1)` on `s2` 
	- Maintain frequency count and check if matches s1 for each window
	- Do an initial one
		- Then just add and subtract the bounds of windows

**Finished notes:** 
- Note → comparison of lists of fixed size (26) is O(1)
	- Goes through and checks one by one
- Could also use matches to compare instead of comparing entire freq list
	- I.e. just compare the added and subtracted bounds values after first initial comparison
	- Lower constant → still O(n) both cases

# References

