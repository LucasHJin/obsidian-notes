---
difficulty: medium
review: true
---
2025-11-24 11:06

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Construct Binary Tree from Preorder and Inorder Traversal

**Preliminary notes:** 
- Preorder → node, left right
- Inorder → left, node, right
- *Note* → need both arrays because you don’t know if it skips
	- I.e. for inorder it could be L, N, L2 instead of L, N, R
- **USE THIS:** 
	- https://tree-visualizer.netlify.app/ 

**Finished notes:** 
- In order traversal divides array into 2 halves (split by root node)
	- To find root node → first value in preorder is root node
- Need to find index in inorder → do this with O(1)
	- Use a [[Hashmaps explained]] 
		- Use list comprehension to go through list and put index of each value in
	- Also use DFS to build up the tree
		- Have left and right boundaries for the inorder array (which segment for current subtree) → start with all
			- Then it recursively shrinks as you keep splitting in half l and r
		- Preorder ALWAYS gives root
			- Must be root of some subtree
			- I.e. leafs are roots of themselves, will just keep giving roots of smaller subtrees
		- Index tells you size of left subtree based on inorder
- ![[Untitled_Artwork 25.png]]

# References

