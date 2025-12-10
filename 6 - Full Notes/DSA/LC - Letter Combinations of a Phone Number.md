---
difficulty: medium
review:
---
2025-12-09 14:34

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * (4^n))
**Space complexity:** O(n)
_______
# LC - Letter Combinations of a Phone Number

**Preliminary notes:** 
- Make a dictionary with lists corresponding to each of the letters for each number

**Finished notes:** 
- Go index by index of digits:
	- Find the value (use as key) → iterate through the hashmap list
	- Binary choice
		- Either add it or don’t and then go to the next value
	- *NOTE* → DO NOT TRY TO PROCESS ALL INDICES IN DIGITS AT THE SAME TIME
- *Note* → use a list instead of string (easier to append/pop)

# References

