---
difficulty: medium
review: true
---
2025-11-28 10:45

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Task Scheduler

**Preliminary notes:** 
- Use a hash table to keep track of the number of each one you need to go through → fast lookup
	- Use a max heap to keep track of the tasks
	- The max tasks get accessed first before any other task
	- `[num, task]` 
	- Then use a greedy approach → keep on popping from the heap and insert into a second heap
		- Only use second heap once first is empty
		- Or repeatedly insert into the same one
		- Use a hash table to keep track of when last updated (compare to overall count)
	- Use idles if the count between uses isn’t high enough
- Ex:
	- {A3, B1, n=2} → can do ABIAIIA or AIIAIBA → in both cases it’s 7
		- 


**Finished notes:** 
- Use a max-heap to track most frequent + count frequency with hashmap (like stated above)
	- BUT → can’t just use greedy
	- Need to keep track of time (make sure interval is long enough)
		- → USE a queue (add in the value and the time when it ends)
		- If the max heap is empty → set counter to the newest value’s time and insert into queue
- *IMPORTANT NOTE* → only need to return total time taken (not any specific CPU)
	- So you don’t need to keep track of the A, B, C… after the hashmap
	- ALSO, note that you have to push into the hashmap if time is up for the queue (because you need to compare against other potential values)
# References

