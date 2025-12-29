---
difficulty: medium
review: true
---
2025-12-29 14:42

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Merge Triplets to Form Target Triplet

**Preliminary notes:** 
- Failure cases:
	- If a value in target is not in triplets
	- If a value in target is smaller than one of the individual target triplets
		- SO → we can ignore any individual triplets which have a value larger than target (or else it will always override)
- Then, check through remaining triplets to see if you can make it
	- Take a greedy approach → if it equals, then it works
	- Don’t need to actually make list either (just check the triplet immediately after verifying it’s valid)

**Finished notes:** 
- *NOTE* → it only asks for true or false
	- So within the remaining triplets, as long as it has the value it ticks it off

# References

