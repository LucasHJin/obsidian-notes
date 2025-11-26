---
difficulty: easy
review: true
---
2025-11-24 15:11

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(mlogk)
**Space complexity:** O(k)
_______
# LC - Kth Largest Element in a Stream

**Preliminary notes:** 
- Know [[Priority queue or Heaps explained]] 
- Use a heap and repeatedly enque/deque?
	- Would not work because then following time you’re missing data

**Finished notes:** 
- Use a heap
	- Keep only k values in the heap
	- If smaller and k filled → don’t add
	- If larger → pop the top and then add to the queue (Ologn)
	- Then at the end, the top value is the kth biggest (because k total and all under are bigger)
- *Note:* 
	- Can just always push into the heap
	- And then only pop if len > k (because it maintains the invariant for you)

# References

