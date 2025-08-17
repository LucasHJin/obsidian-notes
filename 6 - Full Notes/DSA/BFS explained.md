2024-07-30 23:08

Status:
#in-progress

Tags:
[[cp]]
[[cs]]
[[graph theory]]


___________________________________________________________________________
# BFS explained

**What?**
- A method for graph/grid/tree traversal that checks all close nodes before any farther nodes (layer by layer)
	- Does this with a ==togo== queue and a ==visited== set
		- Add first node to togo and visited
		- Find all neighbours, put them in ==togo== and then visit ==each== one, marking them down accordingly
			- Includes their neighbours
		- Do this until all ==visited== and no more ==togo==
- If grid:
	- Use lists with directions (up, down, left, right)
		- `int diffRow[] = {1, -1, 0, 0}`
		- `int diffCol[] = {0, 0, -1, 1}`
	- Also use `isValid()` to check for any invalid grids (i.e. obstacles)
- If [[How do trees work|tree]] → like a graph where there isn’t a cycle
	- Don’t need a visited set → structure guarentees no repeats
	- **Used for:**
		- Traversing a tree top to bottom
		- Care about depth/distance/levels
		- Looking for first match/closest node to root
- If [[How do graphs work|graph]]: (if cycles are possible)
	- Use adjacency list + visited set (to prevent looping over same nodes)
		- Only add unvisited neighbors
	- **Used for:** 
		- Useful for grids, adjacency lists or networks
		- Structure might have cycles/duplicate paths
		- Need to find shortest number of steps
		- Exploring possible states

**General structure:** 
- A [[Data structures explained|queue]] for the current layer of exploration
- A loop to process each node
- A branching step where nodes are added to a queue

**Useful for:** 
- Shortest number of steps
- Clean level-order traversal
- Way to explore everything

**Example:** 
- *Binary tree order level traversal* → Mark down how many elements in the queue and then for each of those elements, add them to the new_level list and add their children to the queue
- *Flood fill* → given an image as a 2d grid and starting from a given pixel → change all connected pixels of same colour to a new colour
	- Create a `visited grid` and traverse with changing (x,y) values → if unvisited, update its colour and add to queue
	- Note → `yield` allows you to return a list of values instead of stopping immediately after first result ([link](https://www.w3schools.com/python/ref_keyword_yield.asp))

# References

