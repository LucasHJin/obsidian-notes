---
difficulty: medium
review: true
---
2025-12-20 16:21

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn)
**Space complexity:** O(n)
_______
# LC - Meeting Rooms II

**Preliminary notes:** 
- Relates to [[LC - Meeting Rooms]] 
- Just want to split it all up so no overlap for any of the individual conference rooms
	- Sort the time intervals list
	- Then have a list tracking all end dates (starting with just 1)
	- Each time → check if the new start date is after any of the end dates → if yes then set it as that new end date
		- Else → just add it as a new end date

**Finished notes:** 
- *Optimal solution:* preliminary solution was O(n^2)
	- **Sweep line algorithm:** 
		- Keep track of a count
			- Each time you reach a start → add to count
			- Each time you reach an end → subtract from count
		- Keep track of the max value of count → this is your answer
		- Implementation:
			- Use either a default dict or a list to keep track of start and end (+1, -1)
			- Then iterate through a sorted version and just keep track of total sum
	- **2 pointer:** 
		- Split into 2 arrays (start and end) and then sort each
		- Then if start is smaller than end add 1 and progress, else sub 1 and progress end array
	- **Min Heap:** 
		- Use a min heap for end of ongoing meetings
		- If meeting starts after earliest ending meeting → reuse the room and push end time to heap
		- Size of heap is answer

# References

