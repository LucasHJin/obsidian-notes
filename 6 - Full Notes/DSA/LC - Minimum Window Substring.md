---
difficulty: hard
review: true
---
2025-08-27 16:24

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n+m)
**Space complexity:** O(m)
_______
# LC - Minimum Window Substring

**Preliminary notes:** 
- Use two pointers
	- Keep track of frequency of each character just like [[LC - Permutation in String]] 
	- But then it’s not of a fixed length
	- Needs to be minimum the same length of `t` but it can also be longer
		- Start from minimum
		- If all in → return True
			- Keep moving left pointer until it turns false
		- Else → while it’s false, start moving the right pointer
- Also track the answer with string + slicing
- To track matching → Just need at least the same amount of t in s
	- AKA → if `t>s` then its false
	- Also keep track of minimum length → only replace if its a new minimum length
- Note → need to be able to handle all upper lower case

**Finished notes:** 
- Logic is mostly right but can improve:
	- Matching
	- String slicing → ONLY SLICE ONCE AT THE END
		- Guarentees O(m+n)
	- Use defaultdict/counter
- Improved logic:
	- **Keep the indexes for string slicing in a list and just keep updating it (O(1))**
	- **Use a counter of the amount of frequencies satisfied vs the amount of frequencies needed**
		- Increment if equality is achieved for a character
		- When `have = needed` → perform same logic as in preliminary (while it’s still true, move the left counter, update the string slicing, update the counter for have if necessary)

# References

