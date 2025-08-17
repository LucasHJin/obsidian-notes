2025-08-16 17:56

Status:


Tags:
[[lc]] 
[[dsa]] 


_______
# Priority queue or Heaps explained

Special type of [[Data structures explained|queue]] where elements are removed in order or priority (not just order they were added)
- Usually implemented as binary heaps (binary trees stored in arrays)
- **Min heap** → every parent is smaller than its children
	- Default in python
- **Max heap** → every parent is bigger than its children
	- Can simulate it by negating all values (smallest positive = biggest negative)
- *Insertion / Removal* → O(log n)

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

