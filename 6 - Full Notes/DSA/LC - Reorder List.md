---
difficulty: medium
review:
---
2025-08-30 12:27

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Reorder List

**Preliminary notes:** 
- Reorder so that it alternates with nodes from the front and back
- *Note:* Can only change the node values themselves (not modify value)
- First thought:
	- You can’t use 2 pointers because you only have the head
	- Idea 2: use temporary variables
	- Need to just perform a [[LC - Reverse Linked List|reverse]] on the second half of the list and then merge the two

**Finished notes:** 
- Use [[LC - Linked List Cycle|fast/slow pointer]] to find midpoint and then [[LC - Reverse Linked List|reverse]] second half of list before combining by intertwining
	- To intertwine → depends on length of second (first will always be 2x)
		- While the second exists, save the next values as temp, set `l1.next` to `l2` and `l2.next` to the original `l1.next` 
- *Note* → after finding `p1` → we want the value after it
	- Set a reference to `p1.next` and then set it to None
	- This makes sure that when combined, there is no cycle/hidden connection
- *Note* → can start with `next.head` for the second pointer
	- Stops right at the end of first list

# References

