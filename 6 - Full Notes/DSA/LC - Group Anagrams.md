---
difficulty: medium
review: true
---
2025-08-16 20:01

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(m+n)
**Space complexity:** O(m)
_______
# LC - Group Anagrams

**Preliminary notes:** 
- Make a list of a bunch of hashmaps (add them to a list each time)
	- Add the word as one of the terms
	- Go through the list in O(n^2) and if they’re the same → add the word
- For all of the same anagrams → combine them
- THOUGHT #2:
	- Have a hash set → compare to value in hashset, if they are already there, they are the anagram of something else
- THOUGHT #3:
	- Have a hash map → word is key, dictionary is value
	- Compare the values

**Finished notes:** 
- Create a hash table using a normal list INSTEAD of a hash map (just use a hashmap for the overall holding)
	- This allows you to convert it into a tuple → use this as a key to append the word to the list of hashmaps
	- Return the hashmap’s values as a list later on
- ^ Essentially same idea as Thought #3 except you need to recognize that you keys need to be immutable

# References

