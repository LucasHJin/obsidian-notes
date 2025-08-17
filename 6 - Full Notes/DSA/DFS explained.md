2024-07-30 23:17

Status:
#in-progress

Tags:
[[cs]]
[[cp]]
[[graph theory]]


___________________________________________________________________________
# DFS explained

**What?**
- A method for graph/grid/tree traversal that checks down one 'lane' completely before the next (goes all the way down and then back up)
	- Going deep (only backtrack when you reach end of path)
- For grids:
	- Use lists with directions (up, down, left, right) and isValid 
	- Go through each of the cardinal directions and immediately recursively call that function
		- Do this until all visited
- For [[How do trees work|trees]]: (acyclic)
	- Check if none → if not, check for target
	- If not target → keep on checking down left side until you find it or backtrack and try the right
	- **Useful:** 
		- Flattening trees
		- Building/checking structures
		- Searching for nodes based on custom logics
- For [[How do graphs work|graphs]]:
	- Use adjacency lists again
	- Then, you can make a function that recursively calls itself
		- Have it check through the neighbours and then for each of the neighbours, call the function for them and so on and so forth until all neighbours of the original node have been investigated (don't forget to mark as visited)
			- This will ensure that you immediately go down a path instead of after all on the same layer
	- **General logic:**
		- for each neighbour node → if not explored, mark as visited and then add it to the recursive call stack
	- **Useful:** 
		- Puzzles and state exploration
		- Graph colouring
		- Recursive traversal
		- Backtracking 
- *Note:*
	- Most of the time → implemented recursively
	- Sometimes iteratively with an actual stack

**Usecases:** 
- [[Topological sorting explained]] 
- Exploring every possibility
- Want to visit all nodes
- Care about structure (NOT DISTANCE)

**Examples:** 
- *Maximum depth of binary tree* → if its the root, return 0, else return the max between the left and right subtrees and add 1 to it
- *Number of islands* → given a 2D grid of 1s and 0s → count how many separate 1 islands there are
	- Setup the getting neighbours function just like in [[BFS explained|bfs]] with the delta x,y
	- If it’s water → return
	- Else → recursively call DFS on the neighbours of an island until there is nothing left to explore
	- *Note* → mark as visited to prevent double counting
 


# References
https://courses.cs.washington.edu/courses/cse326/03su/homework/hw3/dfs.html
