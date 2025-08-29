---
difficulty: hard
review: true
---
2025-08-27 22:14

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn) → O(n) with deque
**Space complexity:** O(n)
_______
# LC - Sliding Window Maximum

**Preliminary notes:** 
- Want an array of all max values from each sliding window
	- I.e. of all the elements in the window, what is the max
- You can’t just use max of each individual list
	- Would be O(n * k) → want O(nlogn)
	- To do this → use a [[Priority queue or Heaps explained|priority queue]]? (FIFO)
	- Max heaps are useful → because you can get max value of the window in O(1) time (just the top of the list)
		- Add the value and the index
		- Only care about the max value → if out of index, remove it and continue until in index and then check against newest value

**Finished notes:** 
- Use deque instead of heap
	- Then it uses an actual sliding window
	- Maintain the deque in decreasing order (front is max, back is min)
	- Perform the following checks:
		- Remove the values at the back while they are smaller than the current value (and then add it)
		- If the front value is outside the range of the window → remove it
		- If the sliding window is big enough (based on `r`) → add it to answer and shift the left bound
		- Then move the right bound
- **MONOTONICALLY DECREASING QUEUE** 

# References

