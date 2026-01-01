---
difficulty: medium
review:
---
2025-12-31 15:49

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Valid Parenthesis String

**Preliminary notes:** 
- Keep track of a counter
	- A left bracket is equivalent to adding one
	- A right bracket is equivalent to subtracting one (want to be neutral at the end)
	- A star can be anything → greedily choose it to always be a left bracket
		- But also keep track of amount of stars total
	- At the end:
		- If 0 → it was already balanced
		- If >0 → subtract stars if it’s 0 now then it’s balanced
		- Else it’s never balanced

**Finished notes:** 
- *Note* → above strategy fails because order matters
	- I.e. `))((` would get 0 but order is wrong
- Instead → track possible number of open parentheses (smallest and largest amount)
	- Stars → smaller amount decreases (i.e. can close it off by having it be a `)`), larger amount increases (i.e. can open a new set with `(`)
	- Want 0 to be in this range → means its possible to have that many open parentheses
	- *Note:* 
		- If high ever goes below 0 you know it’s failed because too many right brackets
		- And you can clip low to 0

# References

