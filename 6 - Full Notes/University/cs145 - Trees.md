2025-09-18 10:31

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Trees

**Trees:** one of the most prevalent data structures in computer science
- Large number of variants for specific purposes
	- Basic terminology + structure is consistent

**Binary tree:** either an empty tree (`empty` or `'()`) or a *node* containing two trees as *children* 
- **Children** → distinguished by `left` and `right` 
- **Undecorated BT:** has just the structure (i.e. just shows the nodes)
- **Decorated BT:** has data in addition to just structure (i.e. a number at each node)
- **Implementation:** 
	- ![[Untitled_Artwork 3.png|500]] 
- **Anatomy of a tree:** 
	- *Root:* a node which is not a subtree of any other node
		- Each non empty tree has exactly one root
	- *Leaf:* a node with no non-empty children
	- *Internal node:* a node with non-empty children
		- Root *can be* an internal node
	- *Path:* a sequence of nodes connected by adjacency
	- *Length of a path:* the number of nodes on a path
	- *Depth of a node:* the length of the path from the root to a specific node
		- Inclusive of the root node
		- *Depth 1* → both a root and leaf (just a dot)
		- *Depth undefined (OR 0)* → just $\epsilon$ 
	- ![[Untitled_Artwork 4.png]] 
- **Size and height:** 
	- **Size:** number of nodes in T
		- 0 if T is empty
		- Else `size(L)+size(R)+1` if non empty
	- **Height:** maximum depth of any node in T
		- 0 if T is empty
		- `max(height(L), height(R))+1` if non empty
- **Maximal height:** a tree with *n* nodes such that no other tree with *n* nodes has a greater height
- **Minimal height:** a tree with *n* nodes such that no other tree with *n* nodes has a lesser height

| height | min size | max size |
| ------ | -------- | -------- |
| 0      | 0        | 0        |
| 1      | 1        | 1        |
| 2      | 2        | 3        |
| 3      | 3        | 7        |
| $n$    | $n$      | $2^n-1$  |

| size | min height                    | max height |
| ---- | ----------------------------- | ---------- |
| 0    | 0                             | 0          |
| 1    | 1                             | 1          |
| 2    | 2                             | 2          |
| 3    | 2                             | 3          |
| 4    | 3                             | 4          |
| 5    | 3                             | 5          |
| $n$  | $\lfloor{log_{2}n}\rfloor +1$ | $n$        |

- **Full binary tree:** a binary tree where each node has either zero or two children
- **Perfect binary tree:** a full binary tree AND all leaf nodes have the same depth
	- ![[Untitled_Artwork 5.png|400]] 





# References

