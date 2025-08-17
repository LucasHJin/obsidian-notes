2025-08-16 15:02

Status:


Tags:
[[lc]] 
[[dsa]] 
[[internship]] 

_______
# Data structures explained

**General structures:**
- **Arrays:** 
	- Reading → **O(1)**
	- Insert/delete → **O(n)**
	- Used in:
		- Traversing a structure in order
		- Accessing specific indices
		- Comparing elements from both ends
		- Sliding window, prefix sums, etc.
- **Linked lists:** every element points to the next one (don’t need to all be beside each other in memory)
	- Reading → **O(n)**
	- Insert/delete → **O(1)**
- **Strings:** basically an array of characters (but immutable → create a new string every modification)
	- Used in:
		- Longest substring without repeating characters
		- Checking if 2 strings are anagrams
		- Return all substrings that match a pattern
		- **MOST hidden as sliding window problems ^** 
- **Sets:** collection of unique values (no duplicates/order)
	- *Insert / Lookup / Delet*e → **O(1)** 
	- Used in:
		- Checking for uniqueness
		- Checking for existence
		- Checking for membership (i.e. in current group)
		- When maintaining a unique sliding window
	- Also called a **HASH SET** 
- **Stack:** last in first out (LIFO)
	- Usually implemented with array or linked list
	- Appending to end, removing from end, checking top or size → **O(1)** 
	- [[DFS explained]] 
- **Queue:** first in first out (FIFO)
	- Usually implemented with linked list or `collections.deque` 
	- Adding to tail, removing from head, checking top or size → **O(1)** 
	- [[BFS explained]] 

**More specific:** 
- [[Hashmaps explained]] 
	- Lookup → **O(1)**
	- Insertion → **O(1)** 
- [[Priority queue or Heaps explained]] 


# References

