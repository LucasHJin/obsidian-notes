2024-07-30 23:10

Status:
#in-progress

Tags:
[[cs]]
[[cp]]
[[graph theory]]


___________________________________________________________________________
# How do trees work

**What?**
- A tree is an undirected graph that is connected and acyclic. This means it has no cycles and there is a path between any pair of nodes.
- Properties:
	- **Acyclic**: Trees do not contain cycles. There is exactly one path between any two nodes.
	- **Connected**: All nodes are reachable from any other node.
	- **Number of Edges**: A tree with `n` nodes has exactly `n-1` edges.
	- **Rooted Tree**: If one node is designated as the root, and all other nodes have a parent-child relationship with respect to this root, the tree is called a rooted tree.

**Types of trees**
- **Binary tree**
	- At most 2 children per node (left and right)
		- **Binary search tree:** left < parent, right > parent
- **N-ary tree**
	- At most N children per node
- **Balanced tree**
	- Height of left and right subtrees of any node differ by **no more than 1**
- **Heap**
	- Special binary tree where parent nodes are ordered based on child nodes
		- I.e. minheap -> the parent node is less than or equal to its children
- **Trie**
	- Stores strings with common prefixes
- [[Spanning tree explained]]



**Traversal**
- [[Disjoint set union explained]] 
- [[Minimum spanning tree explained]] 
- [[In order tree traversal]] (DFS VARIANT)
- [[Pre order tree traversal]] (DFS VARIANT)
- [[Post order tree traversal]] (DFS VARIANT)
- [[Level order tree traversal]] (BFS VARIANT)

# References

