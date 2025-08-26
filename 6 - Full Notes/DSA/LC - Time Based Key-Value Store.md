---
difficulty: medium
review:
---
2025-08-25 15:05

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(1)/O(logn) (set/get)
**Space complexity:** O(m * n)
_______
# LC - Time Based Key-Value Store

**Preliminary notes:** 
- Initial key → a string, then a secondary key in the form of timestamp to get a value
	- For setting → just add it as a tuple/list inside a list
- Use a binary search for the getting
	- Keep track of the answer anytime `mid<timestamp` because it’s the closest one
	- Use a hash table (dictionary)

**Finished notes:** 
- Can assume it’s already sorted from begging (for timestamps)

# References

