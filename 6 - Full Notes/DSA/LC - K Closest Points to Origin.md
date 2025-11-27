---
difficulty: medium
review:
---
2025-11-26 12:02

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogk)
**Space complexity:** O(k)
_______
# LC - K Closest Points to Origin

**Preliminary notes:** 
- Similar to [[LC - Kth Largest Element in a Stream]] 
- Maintain a max heap (negate)
	- If the value is larger (smaller for negative) → don’t add it anymore
- PROBLEM → need to return the point coordinates (not the distance)
	- Use a tuple (first value is what is compared)

**Finished notes:** 
- Can use a tuple or list
- Watch out for using list comprehension too often (time + memory)

# References

