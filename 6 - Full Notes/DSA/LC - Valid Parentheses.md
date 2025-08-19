---
difficulty: easy
review:
---
2025-08-18 11:21

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Valid Parentheses

**Preliminary notes:** 
- Order matters → use a [[Data structures explained|stack]] to make sure that the order is right
	- Example → `{(})` → each time you input an opening bracket, enter it into the stack
	- When it’s the closing bracket → need to match the same order
- Note →
	- Can implement with a list or a deque
	- List is only fast at the back (O(n) at front) but this is all that is needed
	- Deque uses more memory

**Finished notes:** 
- Note → need to consider edge cases because there are many (i.e. if a closing comes first, if no items, etc.)
	- Use a dictionary → makes simpler for comparing
	- 

# References

