2025-09-16 10:44

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Data Structures

**MORE DEEP:** → [[cs145 - Trees]] 

**Atomic types:** only represent one thing
- I.e. numbers, strings → only thing they can store is characters
	- No way to connect 2 of these atomic types together in a meaningful way

**`posn`:** 
- Has an `x` part and a `y` part
	- Can put anything in each of these parts
- **Constructor:** `(make-posn x y)`  
	- Allows us to create a data structure by providing values
- **Selectors:** `posn-x`, `posn-y` 
	- Allows us to retrieve values from the posn
- **Predicate:** `posn?` 
	- Allows us to determine if it’s the posn data structure
- **Notes:** 
	- Use cases → Distance, dates, type-checking, birth dates
		- (Note → racket doesn’t catch with different data types so it’s up to the user)
	- Can nest `posn`’s inside each other → allows us to store an arbitrary amount of data in a stucture
```js
(define (distance p1 p2)
  (sqrt (+ (sqr (- (posn-x p1) (posn-x p2)))
           (sqr (- (posn-y p1) (posn-y p2))))))
```

**`define-struct`**: another [[cs145 - Racket Syntax and Numbers|special form]] (like define)
- Allows you to make a custom structure with a name and then parameters
	- `(define-struct name (n1 n2 n3))` 
- Attach a `-parameter` to access the specific value (selectors)

**Abstraction:** remove inessential details and only focus on the core (shared/essential/general) details

**Abstract Data Type (ADT):** a set of values together with operations on those values/set
- Independent of the actual implementation/programming
- Use cases:
	- Allows to work more generally
	- Allows collaboration
	- Allows protection/hiding information
**Bunch ADT:** allows us to store a multiset of values (with the following operations)
- **Constructors:** 
	- `singleton-bunch` → bunch with a single value
	- `combine-bunches` → combines bunches together into a singular bunch
	- ![[Untitled_Artwork.png]] 
		- And `empty-bunch` 
- **Queries:** 
	- `empty-bunch?` → is the bunch empty
	- `count-bunch` → total amount of elements in the bunch
	- `(count-in-bunch x y)` → amount of `x` in the bunch `y` 
- **Removal:** 
	- `remove-from-bunch` → remove ALL instances from the bunch
- *NOTE* → need to consider efficiency
	- YOU NEED TO IMPLEMENT THIS YOURSELF
		- GIVEN AN ABSTRACT DATA TYPE → on a test
- ![[Untitled_Artwork 2.png]] 

# References

