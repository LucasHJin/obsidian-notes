---
difficulty: medium
review: true
---
2025-08-18 10:39

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Longest Consecutive Sequence

**Preliminary notes:** 
- Can’t use sorting → that takes O(nlogn)
- Notice that only certain numbers can be a sequence (need to be the first → no n-1)
	- Convert to a set (O(n)) → that way u can have O(1) lookups
	- Once you find a no n-1 → repeatedly check for n+1 until it fails using a while loop
		- This is O(n) → each one can only be visited max twice because it starts the repeated check only from first

**Finished notes:** 
- Could technically also use a hashmap → then it doesn’t linearly walk through the entire array (just merges in O(1)) - i.e. doesn’t check one by one

# References

