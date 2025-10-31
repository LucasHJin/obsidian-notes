2025-10-28 10:04

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Infinite Sequences

**Generalizing tail recursion:** 
- Parameters to be modified
	- **initial** - list of arguments
- A condition to examine in the base case
	- **done?** - fxn
- A series of functions/expressions that modify the parameters for the recursive call 
	- Because nothing is happening on the recursive call itself
	- **step** - fxn
- A function/expression that determines what to produce in the base case
	- **final** - fxn
- *NOTE* → can be generalized to a basic generate (for all tail recursion)
```
;; generate: (listof X)
;;           ((listof X) -> Bool)
;;           ((listof X) -> (listof X))
;;           ((listof X) -> Y)
;;           -> Y
(define (generate initial done? step final)
  (cond
    ((done? initial) (final initial))
    (else (generate (step initial) done? step final))
    )
  )
```


**Example:** sumto
```
(define initial (list 10 0))
(define (done? lst) (zero? (first lst)))
(define (step lst) (list (sub1 (first lst)) (+ (first lst) (second lst))))
(define (final lst) (second lst))

(define (newsumto n)
  (local
    ((define initial (list n 0))
     (define (sumto2 initial)
       (cond
         ((done? initial) (final initial))
         (else (sumto2 (step initial)))
         )
       )
     )
    (sumto2 initial)
    )
  )

;; One call using generate:
(define (sumto-gen n)
  (generate
   ;; initial
   (list n 0)
   ;; done?
   (λ (lst) (zero? (first lst)))
   ;; step
   (λ (lst) (list (sub1 (first lst)) (+ (first lst) (second lst))))
   ;; final
   (λ (lst) (second lst))
   ))
```

**Example use cases:** 
- Factorial, fibonacci, number of fibonacci numbers, list of fibonacci numbers

**Infinite sequences:** 
- Racket only allows finite sequences (i.e. lists)
	- Need to calculate as we go
- Can store away to generate the next one
- Examples:
	- **Fibstream:** an ADT that will be a stream containing fibonacci numbers
		- `fibfirst` → returns desired value
		- `fibrest` → returns rest of the values
		- Stream → allows you to make infinite
	- Random → can call random as many times as you want
	- Read → consumes *standard input* and tokenizes it by white space
		- Gives a stream of symbol tokens (one at a time)

**Deferred computation:** when you delay calculating a value (instead of doing it immediately)
- I.e. you can define a function with calculation as the body
	- `(define (val x) (length (build-list 9000000 add1)))` 
	- *Note* → you don’t need the parameter in full racket (can write without the x)
- **Promise:** make a function and promise it gives you a value if it is called
- **Call:** application of the promise (only calculates if necessary)
- **Use cases:** 
	- Functions always evaluate all of their arguments first
		- Can pass these promises as arguments
	- In stream:
		- Make a promise for the `next` field whenever creating a new stream pair

**Writing our own if:** 
- V1 → use parameters as values
	- Problem: evaluates all 3 arguments fully
- V2 → use parameters as promises of values
	- I.e. `(my-if true (lambda () 5) (lambda () (/ 5 0)))` → defers computation of the two functions until needed

**Example:** `((λ (x) (x x)) (λ (x) (x x)))` 
- Repeatedly creates the exact same expression over and over again

# References

