2025-10-30 11:03

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Lazy Racket and Lambda Calculus

**Lazy Racket:** version of racket where computation of results of functions/lambda expressions are delayed whenever possible (everything is a [[cs145 - Infinite Sequences|promise]])
- **Benefits:** 

**Lists in Lazy Racket:** 
- All lists behave like streams 
	- Promise that `rest` has more values that will be given when called
	- Can’t see whole list → only first
- Ex. `(define r (cons 3 r))` will make an infinite list of 3 in LR
	- Because it’s lazy → when it’s called, it produces the next value
- Ex. `(define (f x) (map add1 x))` and `(define z (cons 1 (f z)))` 
	- Can make infinitely long list of whatever function you want

**Example function application:** 
- `(define (triple x) ()+ x x x)`, `(define t 4)`, `(triple (add1 t))` 
```
(+
 (add1 t)
 (add1 t)
 (add1 t))

(+
 (add1 4)
 (add1 4)
 (add1 4))

(+ 5 5 5)

15
```
- Arguments are passed unevaluated
- All occurrences of the same expression are evaluated simultaneously 



# References

