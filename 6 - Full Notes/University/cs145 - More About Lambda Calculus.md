2025-11-07 10:52

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - More About Lambda Calculus

**Stepping practice:** 
`((λx. λf. f x) (λq. f)) (λa. a a)`
- `(λ f. f x)[x <- (λq. f)] (λa. a a)` 
- `(λ g. g x)[x <- (λq. f)] (λa. a a)` (ONLY CASE YOU NEED TO DO [[cs145 - Lazy Racket and Lambda Calculus|ALPHA EQUIVALENCE]])
- `(λ g. g (λq. f)) (λa. a a)` 
- `(g (λ q. f))[g <- (λa. a a)]` 
- `(λa. a a) (λq. f)` 
- `a a [a <- (λq. f)]` 
- `(λq. f) (λq. f)` 
- `f [q <- (λq. f)]` 
- `f` 
Can skip the square bracket stuff

**Notation:** 
- `true -> λx. λy. x` 
- `false -> λx. λy y` 
- `if -> λs. λa. λb. (s a b)` 
- I.e. `(if true a b)` 
	- `(λs. λa. λb. (s a b) (λx. λy. x) a b)` 
	- `(λx. λy. x a b)` 
	- `(λy. a) b`
	- `a` 


*Note* → if you can write a Racket program using only translatable things, you can write an equivalent lambda calculus program
```
(define (and a b)
	(if a b false))

(define and (λa. λb ((λs. λx. λy. s x y) a b (λx. λy. y))))
```


# References

