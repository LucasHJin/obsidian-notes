---
difficulty: medium
review:
---
2025-08-23 17:10

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(log m * n)
**Space complexity:** O(1)
_______
# LC - Search a 2D Matrix

**Preliminary notes:** 
- Apply the same concept of a [[Binary search explained|binary search]] but just a bit trickier for updating the left and right counters
	- Just use normal numbers alongside modulus and division (flatten into 1d list)
		- Based on the normal index → `matrix[n//length][n%length]` 
		- Convert back like above ^^

**Finished notes:** 
- Could technically do a 2 pass binary search
	- First find potential row (segment into portions)
	- Then find the value in the specific row

# References

