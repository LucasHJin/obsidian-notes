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

**Fibstream:** an ADT that will be a stream containing fibonacci numbers
- `fibfirst` → returns desired value
- `fibrest` → returns rest of the values
- Stream → allows you to make infinite



# References

