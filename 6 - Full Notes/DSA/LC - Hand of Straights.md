---
difficulty: medium
review: true
---
2025-12-28 15:52

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn)
**Space complexity:** O(n)
_______
# LC - Hand of Straights

**Preliminary notes:** 
- Must be mod group size
- Can combine into a hashmap of each value and how many times it appears
- Can go through the sorted hashmap:
	- If it’s not continuous → false
		- Can check by making sure the values have same distance between
	- If it is used up → remove (popleft)
	- Else → keep in array and then try again next iteration
	- 

**Finished notes:** 
- Use a min heap for the key values
	- This allows you to find minimum start
	- And then each time just add 1 and check if it still exists in the dictionary
	- And pop whenever you make a group
	- *Note* → if you try to pop a value from min heap that’s not the minimum, you’ve already failed
		- Because then you can’t break it up because your previous one will need it

# References

