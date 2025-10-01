2025-09-25 10:12

Status:


Tags:
[[uni]] 
[[cs]] 
[[cs145]] 


_______
# cs145 - Lists

**Structures are useful but:** 
- They have a fixed set of fields (under names)
- Need explicit fields to connect to other structures (i.e. `node-left`)

**`list`:** racket version of a [[Data structures explained|linked list]] 
- **Definition:** either
	- empty OR
	- `(cons e L)` where `e` is any type of element and `L` is a list
		- Construct with `cons` 
		- Select with `first` and `rest` 
	- *Note* → is a recursive structure (adding on 1 item at a time to the list)
- ![[Screenshot 2025-09-25 at 10.17.43 AM.png|400]] 
	- Is a linearly defined data structure
	- ([[cs145 - Trees|Binary trees]] are binary defined data structures)
- **Characteristics:** 
	- `(first (cons e L)) ⇒ e` 
		- *Note* → L must be a list
			- Can return a list or an element
	- `(rest (cons e L)) ⇒ L` 
		- `rest` ALWAYS produces a list (empty or a list with the rest of the elemnts in the list)
		- Is still in the recursive style
	- Can use both to access terms
		- I.e. `rest` n-1 amount of times and then `first` 
		- OR → just use `second`, `third`, up to `eigth` 
- **Predicates:** 
	- `empty?` → checks if it’s empty (empty list)
	- `list?` → checks if it’s a list (type predicate)
- **Nesting lists** → can have `e` be a list
	- Can represent a binary tree like this
	- Can access still with `first`, `rest` 
- ***NOTE***: 
	- there is a function `list` that can take an arbitrary number of elements as an argument
	- ==NOT== THE SAME AS `cond` 
		- Cond takes 1 element in front of an existing list
		- List takes all elements and puts them in a list
			- Means you can’t access anything past `first` (i.e. no second)
	- *Useful* for testing functions with longer lists (because you only use `first` in recursion)
		- Don’t use within functions (can’t use lists recursively)
	- ![[Screenshot 2025-09-25 at 10.54.16 AM.png]]
- **`list-ref`:** 
	- Returns element at ith index (0-indexed)
	- `(list-ref L i)` 
- **`length:`** 
	- Returns number of elements in the list
	- `(length L)` 
		- I.e. `empty?` is faster than `zero? length` 
- *NOTE* → both of these are ==non-elementary functions== 
	- Time complexity is proportional to the length of the list (**inefficient**)
- **`member`:** 
	- Checks if an element is in the list
- **`append`:** creates a list containing every element in `L1` followed by `L2`  

**Writing our own `list-ref`:** Recurses on natural numbers (0 or add 1 of n where n is a natural number)
- Like peeling away layers to get 0
**Writing our own `length`:** Recurses on lists (empty or cons)
- Like peeling away layers to get to `empty` 
```js
(define (my-list-ref L i)
  (cond
    ((zero? i) (first L))
    (else (my-list-ref (rest L) (sub1 i)))))

(define (my-length L)
  (cond
    ((empty? L) 0)
    (else (add1 (my-length (rest L))))))
```

**List Types:** 
- **Contracts:** formalizes the name, the number and type of arguments, and the type of the produced value
	- I.e. `;; func-name: type-arg1 ... type-argn -> produced-type` 
	- Defining input and output types
- Just like how you can do `(listof Nat)` to only have natural numbers
- EX:
	- `;; length: (listof Any) -> Nat` 
	- `;; bst-insert: Num BST -> BST` 
	- `;; add1: Num -> Num` 
	- `;; member?: Any (listof Any) -> Boolean` 

**Beginner Student with List Abbreviations** → just list instead of cons…


 ![[Untitled_Artwork 8.png|340]]  ![[Untitled_Artwork 9.png|340]] 
# References

