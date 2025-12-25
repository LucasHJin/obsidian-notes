---
difficulty: medium
review: true
---
2025-12-24 14:30

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Jump Game

**Preliminary notes:** 
- Just greed by always taking the maximum jump?
	- If you can’t reach it then it’s guarenteed fail
	- DOESN’T work → i.e. 2201, if you do 1, 2 you get to final
- Want to make some sort of consistent decision
	- Can you reach point B from point A

**Finished notes:** 
- Start from the end index
	- If you can reach this end index from a certain value → update it to that value’s index
	- Keep on going backwards until you reach the start (end index should be 0 by the end)
- *REASONING FOR WHY IT WORKS:* 
	- The key note is that if an index further away can reach the end, it can also reach the closer end
		- I.e. 3, 2, 0
		- 2 can reach 0 so it is updated from index 2 to index 1 but then 3 can obviously reach 2 if it can reach 0 so then it’s updated to index 0 and so it’s a success
			- So you never miss out on a case
		- Once you can reach a closer good index → guaranteed to reach last good index

# References

