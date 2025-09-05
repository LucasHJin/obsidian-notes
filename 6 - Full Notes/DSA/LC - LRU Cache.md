---
difficulty: medium
review: true
---
2025-09-04 09:53

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(1)
**Space complexity:** O(n)
_______
# LC - LRU Cache

**Preliminary notes:** 
- [LRU Cache](https://en.wikipedia.org/wiki/Cache_replacement_policies#LRU) → discards the least recently used items first
	- Basically just a key-value store where there is a certain amount of allocated space/memory and if it’s used up, remove the oldest accessed values
- Use a doubly linked list → each node is the key-value pair
	- Head = least recently used, Tail = most recently used

**Finished notes:** 
- *Note* → need to define an entirely new doubly linked list Node class
	- Need to make a remove + insert function where the node is removed and then inserted in a new place and the `next` and `prev` for those nodes are updated
	- Use `self.left, self.right` → dummies to mark the LRU and MRU
- Use a hashmap to link each key to the node
	- Is O(1) lookup + insert
```python
def remove(self, node):
    prev, nxt = node.prev, node.next
    prev.next, nxt.prev = nxt, prev

def insert(self, node):
    prev, nxt = self.right.prev, self.right
    prev.next = nxt.prev = node
    node.next, node.prev = nxt, prev
```


# References

