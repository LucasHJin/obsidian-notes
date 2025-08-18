---
difficulty: medium
review:
---
2025-08-17 11:06

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(m) → m sum of length of all strings, n number of strings
**Space complexity:** O(m+n)
_______
# LC - Encode and Decode Strings

**Preliminary notes:** 
- Split with a space or a non ASCII character

**Finished notes:** 
- Encode based on length of string, a non ascii character, then the string
- To decode → read up until the non ascii character (use a while loop + slicing)
	- Then, read that length of string out and repeat
- WHY THIS IS GOOD
	- Removes problem from pound sign showing up
	- String always starts off with the number and # → so it would be impossible for it to be a problem even if there is a word liek “5#ab”
		- It would be → “4#5#ab” so you read the first delimiter and the ones after doesn’t matter

# References

