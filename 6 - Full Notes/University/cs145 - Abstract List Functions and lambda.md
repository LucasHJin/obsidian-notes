2025-10-02 10:43

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Abstract List Functions and lambda

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
- *Note* → ==There is only actually 1 type of define (with lambda)==
	- Functions (and all other types seen so far) are **first class values:** 
		- Can be bound to a name
		- Can be an argument to a function
		- Can be produced by a function
	- Proof:
		- Binding → `(define double (lambda (x) (+ x x)))` 
		- Argument → `(map (lambda (x) (+ x x)) (list 1 -2 3))` 
		- Produced → 


# References

