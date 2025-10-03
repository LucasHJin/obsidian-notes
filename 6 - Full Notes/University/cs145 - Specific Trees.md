2025-09-23 10:05

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Specific Trees

**Decorated trees:** have more than structure (also data at each node)
- I.e. family tree, numbers, animals, etc.

**Use cases:** 
- Store size/height of subtree for each node
- Don’t need to compute permanently → can store once and use forever
	- I.e. don’t need to count every node for height → can just look at value stored
- **Memoizing:** storing computed values to be used many times (instead of recalculating)
	- New structure → `(define-struct node (size height left right))` 
	- Computing height:
		- `(define (height t) (if (empty? t) 0 (note-height t)))` 
	- Creating a new tree:
```js
(define (merge t1 t2)
	(make-node 
		(+ (node-size t1) (node-size t2) 1)
		(+ (max (node-height t1) (node-height t2)) 1)
		t1 t2))
```

**BInary search trees (BST):** 
- Used to store an ordered set (i.e. `a<b` or `a>b`) → NO DUPLICATES
	- I.e. integers
	- Can be thought of as an [[cs145 - Data Structures|ADT]] 
- Need to store a key in each node
- **Definition:** either
	- empty or
	- a node with key `k` where: (BST invariants)
		- the left subtree is a BST with every key less than `k` 
		- the right subtree is a BST with every key greater than `k` 

**Invariants:** properties of the BST (always true)
- I.e. left and right subtree conditions
- When constructing an ADT → invariant must be maintained
	- When using an ADT → can assume the invariant holds

**BST Find** → try to locate a key in the set
- Just use binary search
- **Pseudocode:** 
	- If empty → return empty
	- If equal → return tree
	- If less → recurse on left subtree
	- If greater → recurse on right subtree

**BST Insert** → find can help with insertion
- Can only insert in one place based off of greater/less than conditions
- Insert at a leaf node (bottom of a tree)
- **Pseudocode:** 
	- If empty → `(make-node e empty empty)` 
	- If e>k → (`make-node k (node-left t) (insert (node-right t) e)`)
	- If e<k → (`make-node k (insert (node-left t) e) (node-right t)`)
	- If e=k → `t` 

**BST Delete** → find can help with deletion as well
- Deleting leaf nodes is easy (just delete it)
- Deleting a node in the middle with 1 child
	- Just promote that 1 child (make it the new node) → produce the subtree
- Deleting a node in the middle with 2 children
	- Find max of left subtree and then overwrite by deleting the max and then moving it up to be the new root
	- Then if it has a left subtree → just do one child strategy (promote its child to take up the place)
		- Call delete again
	- Just make the key of the node you create equal to the max key you find (that’s how you move it up)
- **Pseudo code:** 
	- If leaf → just delete
	- If one child → promote
	- If 2 children → get largest node of left subtree or smallest node of right subtree
		- Guaranteed to always have space in their sub trees
		- Use a helper
			- Keep going right in the left subtree until you find the stopping point `(find-max)` 

**Other BST Functions:** 
- `(bst? t)` → produces true if the tree is a binary search tree
	- Good helper for A4
- `(bst-min-height? t)` → Check if it’s a binary search tree + min height
- `(bst-delete-min t)` → find the minimum and delete
- `(bst-nth-largest n)` → find the nth largest thing in the binary search tree
	- On A5
	- *Note* → can’t just delete max n times to find nth largest

![[Untitled_Artwork 6.png|350]]  ![[Untitled_Artwork 7.png|300]]



# References

