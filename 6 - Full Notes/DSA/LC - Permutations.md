---
difficulty: medium
review:
---
2025-12-03 14:04

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * n!)
- n! permutations, each takes n elements (n for loop)
**Space complexity:** O(n * n!)
- n! permutations, each of length n
_______
# LC - Permutations

**Preliminary notes:** 
- Like [[LC - Combination Sum]] except no sum + diff ordering works (i.e. 1, 2, 3 is different from 2, 1, 3)
- Keep track of the list + length of the list
	- Return if equal to length of total list
- Use a for loop to go through entire list each time → don’t add if it’s already in the list (O(n))

**Finished notes:** 
- Very similar to as detailed above
	- Just have a `used` list made up of booleans (so that checking the value is O(1)) instead of checking `in` 
- *Note* → this is possible because elements are unique

# References

