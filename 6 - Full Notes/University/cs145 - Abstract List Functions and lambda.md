2025-10-02 10:43

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Abstract List Functions and Lambda

**Abstracting common functions** → when you don’t care about specific details and just general implementation
- I.e. if you want to do something to every element
- I.e. if you have a `abs-list` and `sqr-list` function → only difference is the `abs` vs `sqr`
	- Applies first function and then cons on rest

`map:` 
- Abstract list function that applies a function to each element onto a list
	- Consumes and produces a list BUT it uses another function to help do so
- Implemented like:
```js
(define (my-map f L)
	(cond
		[(empty? L) empty]
		[else (cons (f (first L)) (my-map f (rest L)))]))
```
- Can pass functions into other functions (callbacks)

`filter:` 
- Abstract list function that keeps what you want and removes everything you don’t want
	- Consumes and produces a list BUT it uses another function to help do so
- Implemented like:
```js
(define (my-filter pred? L)
	(cond
		[(empty? L) empty]
		[(pred? (first L))
			(cons (first L) (my-filter pred? (rest L)))]
		[else (my-filter pred? (rest L))]))
```

**Function representations in Racket:** 
- For `(define (double x) (+ x x))` 
- Beginning:
	- `double` → error
	- `(double 3)` → `(+ 3 3)`
- Intermediate
	- `double` → function:double
	- `(double 3)` → `(+ 3 3)`
- Intermediate + lambda
	- `double` → double
	- `(double 3)` → `((lambda (x) (+ x x)) 3)` 
		- Name is replaced with function itself (the lambda)

**`lambda` (λ):** allows to implicitly write functions without explicitly defining them 
- I.e. if they have no use case apart from for this one case
- ==Is a [[cs145 - Data Structures|special form]] that produces an anonymous function== 
	- `(lambda (<parameters>) <expr>)` 
	- **Anonymous:** function without a name
- *Note* → ==There is only actually 1 type of define (with lambda)== → `(define double (lambda (x) (+ x x)))` 
	- Functions (and all other types seen so far) are **first class values:** 
		- Can be bound to a name
		- Can be an argument to a function
		- Can be produced by a function
	- Proof:
		- Binding → `(define double (lambda (x) (+ x x)))` 
		- Argument → `(map (lambda (x) (+ x x)) (list 1 -2 3))` 
		- Produced → `(define (make-adder n) (lambda (x) (+ x n)))` 
			- Can then define a function to be make-adder and then call a value `x` on that function 
			- `(define add10 (make-adder 10)) -> (add10 10)=20` 

**Parametric contracts:** connection between types of consumed arguments and produced values
- **Map:** can do this because you know how to write functions (write parameters as functions)
	- `;; map: (X -> Y) (listof X) -> (listof Y)` 
		- Type X (whatever is given)
		- Type Y (whatever is output)
- **Filter:** 
	- `;; filter: (X -> Bool) (listof X) -> (listof X)` 
- **Make-adder:** 
	- `;; make-adder: Num -> (Num -> Num)` 

**Abstracting common functions:** 
`foldr`: 
- Normally it looks like this:
```js
(define (func L)
	(cond
	[(empty? L) base-case]
	[else (combine (first L) (func (rest L)))]))
```
- Abstract list function → `(foldr combine base-case L)` 
	- What to do in the base case (`base-case`)
	- What to do to the first element + How to recursively combine with the rest (`combine`) 
	- `;; foldr: (X Y -> Y) Y (listof X) -> Y` 
	- `(foldr f b (list e1 e2 ... en))` 
		- → `(f e1 (f e2 ... (f en b))` (STARTS WITH `en`) 
- I.e. `(foldr (lambda (fir rror) (+ fir rror)) 0 (list 1 2 3 4))` 
	- Sums up values in the list
	- `fir` → first
	- `rror` → rest result of recursion
- **NOTE:** Starts from the right side for recursion

`foldl`: 
```js
(define (func L) (func-help L init))
(define func-help L acc)
	(cond
	[(empty? L) acc]
	[else (func-help (rest L) (combine (first L) acc))]))
```
- Like `foldr` except it processes from the left (tail recursion)
- Abstract list function → `(foldl combine init L)` 
	- Initial value to start with instead of base case and goes till empty list
- `;; foldl: (X Y -> Y) Y (listof X) -> Y` 
- `(foldl f i (list e1 e2 ... en)` → `(f en (f en-1 ... (f e1 i)))` 

`build-list:` 
- `;; build-list: Nat (Nat -> X) -> (listof X)` 
- Applies `f` to all values of 0 to n-1
- `⇒ (list (f 0) (f 1) ... (f (sub1 n)))` 

`sort:` produces a sorted list of all the elements from `lst` according to the ordering specified by `cmp` `(sort lst cmp)` 
- Note: ANY cmp will work as long as it consumes 2 values and produces a boolean
	- I.e. can use `string<?` or even `random` 
- `;; sort: (listof X) (X X -> Bool) -> (listof X)` 

# References

