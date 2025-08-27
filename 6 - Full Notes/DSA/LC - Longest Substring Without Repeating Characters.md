---
difficulty: medium
review: true
---
2025-08-26 11:38

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(m)
_______
# LC - Longest Substring Without Repeating Characters

**Preliminary notes:** 
- Use 2 pointers → keep increasing the right one until you get a value already existing
	- Then you increase the left pointer until its no longer in there
	- Use a hashmap/set → i.e. hashmap, can keep track of each key
		- And then just remove up until that key

**Finished notes:** 
- More optimal → use a for loop + a dictionary
	- Keep track of most recent index → if duplicate, move l all the way to the new index

# References

