2025-10-09 11:14

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Information Hiding, Modules and Packages

**Information hiding:** separate implementation from interface (user)
- Abstract details of *how* → focus on *what* 
	- Store internally but modify/access externally in a controlled manner
- **Benefits:** 
	- Can more easily preserve invariant properties
	- Can prevent malicious usage
	- Can prevent inadvertent violations
	- Can alter the implementation without affecting the interface
	- Can simplify programs by *modularizing* them

**Modules/Packages in Racket** 
- Need FULL RACKET → choose determine language from source
	- Put `#lang racket` at the top of the fine
	- To share interface (functions/data) → `(provide f1 f2 ... data1 data2 ...)` 
- To use interface → `(require "source-file-name.rkt")` 
	- THIS CAN BE ANY LEVEL LANGUAGE
	- *Note* → if no quotation marks → looks for built in packages

**Using modules/packages effectively:** 
- Maintain invariants by limiting ability of user to access/modify data
	- I.e. only provide some functions
- Helpers should be hidden
- For structures:
	- Use smart constructors (not default) that allow it to hold extra info other than user input

**Structures in modules:** 
- Previous → use it to hold compound data
	- I.e. `(define-struct boo (a b c))` 
	- Places 3 data items into 1 container (boo)
- Modules → can use structures as wrappers to hide data
	- I.e. you could make a struct `account` in module `bank-account` → no accessing the fields within struct
		- Can change implementation later on but code that uses those functions still work
- Usefulness:
	- I.e. there is a function f1 in module A and function f2 in module B → cannot interact with each other except through use
		- How each function works doesn’t affect the other
- Example: manufacturing a car
	- Each person builds stuff and provides it to the next person (don’t need to worry about previous)
		- Each has internal process → doesn’t matter as long as you provide same export

**Information hiding IN RACKET:** 
- `local` → allows you to hide information with a function/local scope
	- Define values locally and use them in a body
```
(local
	[(define t1 expr1)
	 (define t2 expr2)
	 ...
	 (define tn exprn)]
	body)
```
 - Each define is evaluated in order and then body is evaluated with defined names
```
;; x is globally define, at the global scope
(define x 1000)

;; x has local scope in the two examples below
(local [(define x 1)] x)
(local [(define x 2)] x)

;; x in double has "functional" scope
(define (double x) (+ x x))
```
- I.e. the value of x in EACH of these lines is different
	- Local scope is similar to functional scope (new value of x that only exists until the body is fully evaluated)
- *Notes:* 
	- Local can use previously defined functions/variables (both from inside and outside local)
	- Nested locals take priority over external locals (can check with *check syntax*)
```
(local
  ((define x 3)
   (define y 9))
  (local
    ((define y (sub1 x)))
    (+ x y)
    ))
;; GIVES 5 not 12
```
- [[cs145 - Stepping|Semantic rule]] → can check the slides 11 (just removes local and a bracket)
	- For each new name → chooses a new `_N` where N is a new number
	- ![[Screenshot 2025-10-21 at 1.56.34 PM.png|200]] 

**Reasons to use local:** 
- Encapsulation → information hiding
	- Helper functions can be defined locally (only accessible in main function)
		- I.e. tail recursion
```
(define (sum-list L)
  (local
    ((define (sum-list-tail L acc)
       (cond
         ((empty? L) acc)
         (else (sum-list-tail (rest L) (+ (first L) acc))))))
    (sum-list-tail L 0))) 

;; Can't call check-expect inside
;; Still use contracts tho (MANDATORY)
```
- Clarity → naming subexpressions (have constants)
```
(define (dist p1 p2)
  (local
    ((define delta-x (- (posn-x p1) (posn-x p2)))
     (define delta-y (- (posn-y p1) (posn-y p2))))
    (sqrt (+ (sqr delta-x) (sqr delta-y)))
    ))
```
- Efficiency → avoiding duplicate computation
```
(define (max-list L)
  (cond
    ((empty? (rest L)) (first L))
    (else (local
      ((define max-rest (max-list (rest L))))
      (cond
        ((> (first L) max-rest) (first L))
        (else max-rest))))))
;; Now runs in linear time -> figures out recursive call once and then uses it in multiple locations
```




# References

