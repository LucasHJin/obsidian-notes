---
difficulty: easy
review:
---
2025-08-29 15:17

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1) → better than O(n) hashset where you just add it and continue through cycle until seen
_______
# LC - Linked List Cycle

CALLED **Floyd’s Tortoise and Hare Algorithm** 

**Preliminary notes:** 
- Use [[Two pointers explained|two pointers]] → start from the beginning for both, one moves at twice the speed
	- Iterate through until either they are the same (not just value, the entire instance) or reached the end
- *Note* → need to consider if `p2.next` is None, there is no `.next` on top of that
	- Run loop while both `p2` and `p2.next` are true → guards against current being None or the next value being None so you can do a `.next` on both of these

**Finished notes:** 
- *Note* → why is it a linear time complexity?
	- The fast pointer moves 1 closer each time (if there is a cycle)
	- So once they both reach the cycle (at most n steps), then it will eventually be caught up (again at most n steps) → 2n but constant n

# References

