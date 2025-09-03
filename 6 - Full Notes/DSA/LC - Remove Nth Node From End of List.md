---
difficulty: medium
review:
---
2025-08-31 17:56

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** 
**Space complexity:** 
_______
# LC - Remove Nth Node From End of List

**Preliminary notes:** 
- Use a counter to go through
	- When at the n-1th node → set `.next` to the following value’s node and then set the nth node’s to None
	- DOESN’T WORK → this is nth from front
- *Note* → need to do it in one pass
	- Use 2 pointers → only start moving the second one after n steps
	- Move while p2.next is not None → and then just remove the p1.next by changing it to `.next.next` 
 
**Finished notes:** 
- Use a dummy → return `dummy.next` → removes edge cases again (i.e. if n is length of list)
- *Note* → don’t need to worry about removing what nth references because it will not be referenced by anything and cleaned up

# References

