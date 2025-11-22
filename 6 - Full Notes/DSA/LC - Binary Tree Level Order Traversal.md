---
difficulty: medium
review:
---
2025-11-21 14:40

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Binary Tree Level Order Traversal

**Preliminary notes:** 
- Like [[BFS explained]] except it’s for a tree
	- Layer by layer traversal (have a queue - FIFO)?
- Use a queue and just add children (left right) to queue
	- Question → how to check which layer it’s a part of
	- In queue track 2 values (value of node, layer)
		- `deque` → append, popleft
	- If it’s the current layer → add it to the current list
	- Else make a new list

**Finished notes:** 
- *Note* → don’t need to explicitly track layer/level
	- Can just go layer by layer (go through length of queue) → add on all of the following children for that layer 
	- Then go through all of that next layer with another for loop
	- Do this until while loop is finished

# References

