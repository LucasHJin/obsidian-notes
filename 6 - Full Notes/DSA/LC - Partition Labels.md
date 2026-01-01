---
difficulty: medium
review:
---
2025-12-30 20:10

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(m)
_______
# LC - Partition Labels

**Preliminary notes:** 
- What the question is asking for:
	- Keep a string in the same order but just split it into substrings where if you combine them, you get the original string and each letter only appears in the substring once
- *Note* → for each substring, it’s initially based on where the first letter ends
	- But then if the letters inside end later, then we have a new ending
	- So track the last ending index for all letters by using a hashmap and then track for each individual substring until satisfied
		- Then push to an answer list
	- Then you can restart with the next value while there are still characters

**Finished notes:** 
- *Note* → dont worry about edge cases or needing to append at end
	- Because by choosing max of current ending index and from the string, we must eventually reach an index that’s equal to `len(s)-1` 
		- This will naturally satisfy == i at some point (at that point it’s closed)
	- You can never end the algo while open
	- *NOTE* → invariant is that ending index is always preserved
		- So you always need to. update (regardless of if partition end was found or not)

# References

