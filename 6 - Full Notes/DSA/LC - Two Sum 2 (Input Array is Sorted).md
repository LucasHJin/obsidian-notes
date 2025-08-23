---
difficulty: medium
review:
---
2025-08-21 22:06

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Two Sum 2 (Input Array is Sorted)

**Preliminary notes:** 
- Since it needs to be O(1) space → can’t use a hashmap
	- Instead just keep track using pointers?
	- Since it’s sorted → add the two pointer values together (pointers on opposite ends)
	- If it’s too big → subtract right
	- If it’s too small → add left

**Finished notes:** 
- Exactly as described
- Technically → binary search could also work where you let the second value be the middle of left and right and iterate through all values of i
	- But → worse time complexity overall

# References

