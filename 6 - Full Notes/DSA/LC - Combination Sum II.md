---
difficulty: medium
review: true
---
2025-12-02 11:15

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * (2^n))
**Space complexity:** O(n)
_______
# LC - Combination Sum II

**Preliminary notes:** 
- *Note* → no duplicate combinations, only one value per combination
- Just do like [[LC - Combination Sum]] 
	- Except for index advance it forward instead of keeping it the same
	- This fails → i.e. 1, 7 and 7, 1 are the same
		- Sort ahead of time + check if already in list
- Turn it into a set → that way it guarentees only one instance of each value?
	- But then this doesn’t check for if you need to use multiple of the same value
- Use a 2d array?
	- Num + amount
	- So it won’t get stuck

**Finished notes:** 
- Advance index forward + sort at the beginning
- Check WITHIN THE SAME LEVEL OF RECURSION if values are the same
	- In that case skip them
	- Or else it would produce identical results
		- I.e. `[1, 1, 2, 5]` need to sum to 8 → can produce `[1, 2, 5]` 2 ways
	- But don’t skip on deeper levels because you can use the same number (diff value) 
- *Note* → eliminate duplicates similar manner to [[LC - Three Sum]] 

# References

