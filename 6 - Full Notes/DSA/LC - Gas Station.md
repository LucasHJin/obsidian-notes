---
difficulty: medium
review:
---
2025-12-27 14:24

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Gas Station

**Preliminary notes:** 
- Subtract the gas given from the cost at the each stop
	- Add up for total amount of gas gained and used 
	- If negative → impossible (because you’ll never have enough gas for a full loop)
	- ^ This finds if a root is possible but not from where it works

**Finished notes:** 
- If total gas < total cost → impossible
- Else:
	- Still use a running total
	- But instead → if total ever becomes negative → shift to next index because you can’t start from prior (or else it will never add up to enough)
	- I.e. if you have +1 +2 -4, regardless of if you start at index 0, 1 or 2, they all fail

# References

