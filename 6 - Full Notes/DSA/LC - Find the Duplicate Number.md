---
difficulty: medium
review: true
---
2025-09-03 08:24

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Find the Duplicate Number

**Preliminary notes:** 
- *Note* → need to use only constant extra space and not modify the array
	- Can’t use a set/hashamp → takes up extra space
- Maybe → use a fast/slow pointer setup
	- If reach the end → iterate back through the list
	- Keep on doing this until the pointers match up?
		- This is O(n^2)

**Finished notes:** 
- Can mark as negative
- Fast/slow setup:
	- Called **Floyd’s Cycle Detection** 
	- Pretend it’s like a linked list → visit the index pointed to by the value itself
		- Works because `1≤num[i]≤n` 
	- If the two values meet → it’s a [[LC - Linked List Cycle|cycle]] 
	- Then you just need to find where the cycle starts (will be the duplicate value because it’s what gets pointed to by multiple other values)
		- Do this by resetting the fast pointer and then moving again (shift each by 1)
- `distance(start → entrance) = distance(meeting → entrance) % cycle length` 
	- ![[Screenshot 2025-09-03 at 7.14.00 PM.png]] 
		- Just change the `p+2c-x` to `p+nc-x` 

# References

