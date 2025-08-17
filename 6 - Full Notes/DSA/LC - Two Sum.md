---
difficulty: easy
---
2025-08-16 19:50

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Two Sum

**Preliminary notes:** 
- 

**Finished notes:** 
- Use a single hashmap with a single pass → calculate the difference remaining after it and check if it is already in the hashmap (already seen)
	- If not → add the value itself to the hashmap with its index as a value and then check the next value
- *Better than* → two pass where first time you get all the values and second time you check for difference

# References

