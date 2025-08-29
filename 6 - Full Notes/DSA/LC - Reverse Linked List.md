---
difficulty: easy
review: true
---
2025-08-29 13:46

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Reverse Linked List

**Preliminary notes:** 
- [[Data structures explained|Review linked lists]] 
- Go through each value and add it to the list → proceed until you get `None` 
	- Then, go through the list in reverse and make it from that
	- Or → do it while you are doing it
		- I.e. in the process → the first one points to None, then the next one points to the previous one and so forth

**Finished notes:** 
- Track a `prev, curr, next`
	- Start with the current as the head and prev as none
	- While current is existing → track the forward next with `next` and then set the backwards next to `prev` 
	- Then move `prev`, `curr` forward by one
- *Recursive solution:* O(n) space
	- Base case → List is None (empty)
	- Subproblem → only need to reverse 1 node at a time
	- Set the current node’s next pointer to null and what it was originally pointing at, set that next pointer to the current
	- *Note:* 
		- It will go all the way until the end where the `head.next` is nothing
		- Then it returns that as the new head → and u can break and set the new heads with `head.next.next=head` because you are taking the next value of the following element and flipping it
# References

