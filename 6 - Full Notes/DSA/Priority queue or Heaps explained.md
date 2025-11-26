2025-08-16 17:56

Status:


Tags:
[[lc]] 
[[dsa]] 


_______
# Priority queue or Heaps explained

**Heap:** tree data structure where each node is ≤ to its children (min heap) or ≥ to its children (max heap)

Special type of [[Data structures explained|queue]] where elements are removed in order or priority (not just order they were added)
- Usually implemented as binary heaps (binary trees stored in arrays)
	- Complete → all filled except maybe last level
	- For array storage:
		- Root: `i`
		- Left: `2i+1` 
		- Right: `2i+2` 
		- Parent: `(i-2)/2` 
- **Min heap** → every parent is smaller than its children
	- Default in python
- **Max heap** → every parent is bigger than its children
	- Can simulate it by negating all values (smallest positive = biggest negative)
- *Insertion / Removal* → O(log n)

**Operations:** 
- Sift up → keep swapping up while its smaller than its parent (Ologn)
- Sift down → keep swapping down while larger than child (swap with smaller child) (Ologn)
	- Use the above to:
		- Insert – O(logn)
			- Insert at end and sift up
		- Get max/min – O(1)
			- First value
		- Extract max/min (push/pop) – O(logn)
			- Swap with leaf node and delete, then then sift down
		- Update – O(logn) vs O(n) (depends on if you have the index)
			- Sift up/down (compare old/new values)
		- Build (heapify) – O(n)
			- Go through array from reverse and sift down
			- Sift down because more nodes at bottom
			- Reverse so no need to sift again

____
**Heapsort:** sorting data structure that uses heap
- Heapify and then repeatedly extract min (O(nlogn))

**Priority queue:** 
- [[Data structures explained|Queue = FIFO]] 
- Main operations:
	- Enqueue - O(logn)
		- Insert
	- Dequeue - O(logn)
		- Extract max
	- Peek - O(1)
		- Get max
	- Change priority - O(logn) / O(n)
		- Use update
	- Is empty? - O(1)
		- Check length = 0

In python → `heapq` 
- ==THIS OPERATES DIRECTLY ON A LIST== 
	- Using the indexing tricks (no need to use a new data structure)

___
**Use cases:** 
- Repeatedly extracting largest/smallest values
- Maintaining a top-k or bottom-k set of values
- Real time ranking, greedy selection, dijkstra path finding, etc.
- Need to sort on the fly faster than O(nlog n)

**Examples:** 
- *K closest points to origin* → given a bunch of points on an xy plane and find k closest to origin
	- Use `heappq` with `heappop` and `heappush` (note → heaps use the first item in tuple to figure out priority)
		- `heap = []` and then push to that heap with `heappush(heap, 1)` 
	- Push distance and then point
		- Pop the smallest element k times to get the k smallest points
- *Kth largest element in an array* 
	- Take all values and negate → turn into max heap
	- `heapify` → rearranges list into new sorted heap


# References

