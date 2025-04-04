2024-07-30 20:52

Status:
#in-progress

Tags:
[[cs]]
[[cp]]
[[graph theory]]

___________________________________________________________________________
# How do graphs work

**What?**
- Nodes and edges that are connected (either 1 directional or bidirectional)
	- These edges and/or nodes can be weighted
- Can be represented with:
	- Adjacency List
		- A list where each node has a list of its adjacent nodes. More space-efficient for sparse graphs.
		- I.e. 2D list of size n+1 -> for j from 1 to n, if an edge exists to node i, add value i to index j
	- Adjacency Matrix
		- A 2D array where `matrix[i][j]` indicates the presence of an edge between nodes i and j. Useful for dense graphs.
			- Filled with 1 and 0
			- ![[Screenshot 2024-07-30 at 11.07.28 PM.png|200]]

**Types:** 
- [[Directed acrylic graphs explained]] 

**Examples:**
- Shortest path queries.
- Detecting cycles.
- Finding strongly connected components.
- Network flow problems.

**Paths/traversal**
- Not weighted:
	- [[BFS explained|BFS]]
	- [[DFS explained|DFS]]
- Weighted:
	- [[Dijkstra's algorithm explained|Dijkstra]]



# References
https://www.freecodecamp.org/news/dijkstras-shortest-path-algorithm-visual-introduction/
