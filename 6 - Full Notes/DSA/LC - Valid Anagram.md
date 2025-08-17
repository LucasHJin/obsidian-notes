---
difficulty: easy
---
2025-08-16 19:38

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n+m)
**Space complexity:** O(1)
_______
# LC - Valid Anagram

**Preliminary notes:** 
- Use a hashmap → add the amount of each character to the hashmap
	- If its the same for each → anagrams
	- Else → not
- Also use a set in the first check through → then immediately if not in set you can stop it
	- Scrap this → can directly compare dictionaries in python

**Finished notes:** 
- Could have compared length of them to begin with
	- Only go through if same length → also means only 1 pass through
- *Alternate solution* → hash table
	- Implement using the difference in value ASCII

# References

