2025-10-23 13:02

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Total Order and Sorting

**Partial order:** a relation $\preceq$ is a partial order on a set if it satisfies these properties:
1. *Reflexive* → $x\preceq x$ 
2. *Antisymmetric* → if $x\preceq y$ and $y \preceq x$ then $x=y$ 
3. *Transitive* → if $x\preceq y$ and $y\preceq z$ then $x\preceq z$ 

**Example:** divisibility
1. $a|a$
2. if $a|b$ and $b|a$ then $a=b$ 
3. if $a|b$ and $b|c$ then $a|c$ 

**Example:** subset
- For a set {1, 2, 3} → all of these are subsets
	- {}, {1}, {2}, {3}, {1, 2}, {2, 3}, {1, 3}, {1, 2, 3}
- {1}, {2}, {3} are indistinguishable in the order compared to {1, 2} or {1, 3}
	- So it’s partial order → only the ends are ordered

___
**Total order:** a relation $\leq$ is a total order on a set S if it satisfies the following properties
- ==3 properties of Parital order== AND
- *Strongly Connected* → Either $x\leq y$ or $y\leq x$ 
	- 1 is redundant because it follows from rule 4
- **Non-strict** total order ^^
	- *NOTE* → $\leq$ doesn’t mean numerically (just a placeholder symbol)

**Example:** real numbers (and any subset of R)
- Key idea → you have a number line (so you can always say that one number is bigger than the other)

**Example:** lexicographical ordering (i.e. a dictionary → a > b)

**STRICT total order:** Given a non-strict total order → can find associated strict total order $<$ by negating rules 1, 2, 4
- *Irreflexive* → Not $x<x$ 
- *Asymmetric* → if $x<y$ then not $y<x$ 
- *Transitive* → if $x<y$ and $y<z$ then $x<z$ 
- *Connected* → if $x\neq y$ then either $x<y$ or $y<x$ 

**Derived relations:** given a total order $\leq$, we can derive:
- ![[Screenshot 2025-10-23 at 1.21.33 PM.png|300]] 

**Equivalence classes:** 
- $=$ forms an equivalence class rather than normal “equal”
- I.e. `(lambda (a b) (< (abs a) (abs b)))` 
	- 10 and -10 are equal because they give same answer (same equivalence class)
	- So if we had `(sort (list 1 5 -5) FXN)` then 5 and -5 would be considered equal
- **Consequence:** 
	- In sorting → we need tie breaking or accept an arbitrary ordering in the equivalence class
	- I.e. can think a circle of points around origin
		- If ordering is decided by distance → all same equivalence class 
		- Tie breaking → if 2 points are same distances, use smaller x

**Key takeaways:** 
- When using $<$ for comparison in BST, we can generalize to use any total order on the keys

___
**Lexicographic Ordering:** when we have compound data, we need to define our own total order (own sorting algorithm)
- Can compare using each element in structure (going from first onwards)
```js
(define (lex< a b)
	(cond
	[(empty? a) (not (empty? b))] // tie so pick a<b
	[(empty? b) false] // true if a comes before b, false otherwise
	[(< (first a) (first b)) true]
	[(< (first b) (first a)) false]
	[else (lex< (rest a) (rest b))])) // if both same
```
- Observations/modifications:
	- Can provide more parameters to customize comparison (other than numerical less than)
		- `(lex< a b <)` and `[else (lex< (rest a) (rest b) <)]))` 
		- I.e. can pass `string<?` for `<` to compare strings
	- Within sort → you now need to pass a lambda
		- Takes 2 arguments, passes them with the comparison function

___ 
**Sorting:** racket implementations
- **Insertion sort:** insert an element into the correct spot of an already sorted list
	- Implementation → use 2 accumulators `remain` and `sorted` to do the processing
	- Invariants (something that is ALWAYS true):
		- `remain` and `sorted` contain all elements to be sorted
		- `sorted` is in sorted order
	- Need a helper called `insert` to insert into the correct spot
		- I.e. should X go in front of Y, no then go to next list up till empty or yes
	- **Analysis:** 
		- Progress → terminates after n steps (each step moves 1 element)
		- Time complexity of removing from remain → O(1)
		- Time complexity of inserting into sorted → O(i) at step i
		- Overall running time → $\sum_{i=1}^{n} O(i) \in O(n^2)$ 

| Step Count | Remain                    | Sorted                    |
| ---------- | ------------------------- | ------------------------- |
| 0          | (30 70 10 80 60 50 40 20) | ()                        |
| 1          | (70 10 80 60 50 40 20)    | (30)                      |
| 2          | (10 80 60 50 40 20)       | (30 70)                   |
| 3          | (80 60 50 40 20)          | (10 30 70)                |
| 4          | (60 50 40 20)             | (10 30 70 80)             |
| 5          | (50 40 20)                | (10 30 60 70 80)          |
| 6          | (40 20)                   | (10 30 50 60 70 80)       |
| 7          | (20)                      | (10 30 40 50 60 70 80)    |
| 8          | ()                        | (10 20 30 40 50 60 70 80) |

- **Selection sort:** select the correct element (max/min) from the list and place in the “next“ location
	- Implementation → use 2 accumulators `remain` and `sorted` 
	- Invariants:
		- `remain` and `sorted` have all elements
		- `sorted` is sorted
		- every element $x$ of `remain` and every element $y$ of `sorted` satisfy $x<y$ 
	- Need a helper to find + remove max from `remain` 
	- **Analysis:** 
		- Progress → terminates after n steps because moves 1 element/step
		- Time complexity of removing from remain → O(n-i) at step i
		- Time complexity of inserting into sorted → O(1)
		- Overall running time → $\sum_{i=1}^{n} O(n-i) \in O(n^2)$ 

| Step Count | Remain                    | Sorted                    |
| ---------- | ------------------------- | ------------------------- |
| 0          | (30 70 10 80 60 50 40 20) | ()                        |
| 1          | (30 70 10 60 50 40 20)    | (80)                      |
| 2          | (30 10 60 50 40 20)       | (70 80)                   |
| 3          | (30 10 50 40 20)          | (60 70 80)                |
| 4          | (30 10 40 20)             | (50 60 70 80)             |
| 5          | (30 10 20)                | (40 50 60 70 80)          |
| 6          | (10 20)                   | (30 40 50 60 70 80)       |
| 7          | (10)                      | (20 30 40 50 60 70 80)    |
| 8          | ()                        | (10 20 30 40 50 60 70 80) |

- **BST insertion sort:** use a BST to sort a list
	- *Algorithm*: give list → insert all elements from list into BST → extract in order (inorder traversal) all elements into a list
	- *Inserting/removing from a BST:*
		- Worst case → O(i)
		- Average case → O(log i)
		- AVL worst case → O(log i)
			- Overall running time → $\sum_{i=1}^{n} O(\log i) \in O(n\log n)$ 
	- *Problem with duplicates:* can’t have duplicates in BST 
		- Solution → keep a count of # of occurrences in BST node (i.e. just like key)

- **Quicksort:** 
	- **Base case:** if given list is empty → produce empty
	- **Else** → pick a random element e from L (**pivot element** → want to pick a “good” one)
		- Form 2 lists S and G where all elements s in S satisfy $s<e$ and all elements g in G satisfy $g>e$ 
		- Recursively call quick sort on both S and G until they all become empty/single list
			- Then append sorted versions with e in the middle
	- ![[Pasted image 20251023140631.png|400]] 
	- **Running time:** 
		- Average → $O(n\log n)$ 
		- Worst case → $O(n^2)$ (selection sort)
			- I.e. if you pick max/min each time → one of partitions is empty and other is all remaining elements
	- **Observations:** Hard to do with tail recursion

**Bottom-up merge sort:** WHAT THE RACKET SORT ALGORITHM ACTUALLY DOES
- **Idea** → merge 2 sorted lists into one sorted list
- **Implementation** → inside a new list `acc`, create sorted lists of size 1, 2, 4, … merging to form larger lists
- Invariants:
	- `acc` → list of lists (containing elements to be sorted)
	- Union of all elements in `acc` is the original list
	- Each element of `acc` is sorted
- Helper → `merge` (takes 2 sorted lists and combines them into 1 sorted list)
	- To merge → start with picking the first terms (smaller term isn’t going to be second) and then just move the terms and pick smallest elements and repeat
- **Analysis:** 
	- Progress → $\log_2 n$ steps
		- At each step, we have k lists becoming k/2 lists (approx)
	- Overall running time: $O(n\log n)$ 
- **Why bottom up?** 
	- Start from smallest to biggest

| Step Count | acc                                       |
| ---------- | ----------------------------------------- |
| 0          | (30 70 10 80 60 50 40 20)                 |
| 1          | ((30) (70) (10) (80) (60) (50) (40) (20)) |
| 2          | ((30 70) (10 80) (50 60) (20 40))         |
| 3          | ((10 30 70 80) (20 40 50 60))             |
| 4          | (10 20 30 40 50 60 70 80)                 |

**Top-down merge sort:** 
- If L is empty, produce empty
- Else → divide the list into 2 equal halves, and merge sort each half, merging the resulting two lists together
	- Go all the way down and then all the way back up
- Bad for racket → no way of easily getting to middle element of the list


# References

