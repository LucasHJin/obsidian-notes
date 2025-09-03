---
difficulty: medium
review: true
---
2025-09-01 17:41

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Copy List with Random Pointers

**Preliminary notes:** 
- **deep copy** → fields are dereferenced
	- No references to objects being copied, all new copies of objects created
	- *Note* → can’t just iterate through and make a random pointer to a node because it might not exist yet

**Finished notes:** 
- Use a hashmap to track copies of all nodes and assign the random pointers after an initial first pass of creating all the copies
- **Steps:** 
	- Use a first pass → create copies for all nodes and map each old node to a new copy
	- Second pass → connect all the pointers for the copies
- *Note:* could make it one pass
	- Use defaultdict → use a lambda to automatically create a Node(0) placeholder if passed in and not in the dict yet
	- Then do all the copying stuff like normal (fixes itself over time)

# References

****