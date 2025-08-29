---
difficulty: easy
review: true
---
2025-08-29 14:19

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n+m)
**Space complexity:** O(1)
_______
# LC - Merge Two Sorted Lists

**Preliminary notes:** 
- You want to merge them in a non-decreasing order
- Check each of their current values to see which points to which (which is greater) and then advance to the next node
	- If they are the same → check the following values

**Finished notes:** 
- Use a moving pointer (`node`) that represents the last element of the merged list being created
	- Each time → compare the two linked lists and add the smaller value to the `node.next` 
	- Then, move the node forward and the added linked list forward
- Edge case → at the end, add whichever is still remaining (still has values)
- *NOTE* → create a `dummy=ListNode()` and then build the merged list off of that
	- So that you don’t have to worry about edge cases (i.e. what is the head of the merged LL) → just return `dummy.next` at the end so the `0` at the head doesn’t get returned as well

# References

