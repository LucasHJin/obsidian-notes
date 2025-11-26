2025-11-20 13:41

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Building A λ-calculus Interpreter

Relates to [[cs145 - Big Picture of How Programs Work]] 

**Binary Arithmetic Expression:** is either:
- a number, or
- an expression of the form `(op arg1 arg2)` where
	- op is `+, -, *, /` 
	- arg1, arg2 are BAExp
- *Evaluated bottom up (from leaf nodes)* 
	- Internal nodes must be operators
- `(define-struct baexp (op arg1 arg2) #:transparent)` 
	- `#:transparent` → allows us to see inside the structs
- ![[Untitled_Artwork 24.png|400]] 

**Match:** a function that takes an argument and determines if it matches a certain structure → then produces a part of the structure as needed
- Like cond (is X equal to Y)
- Can look at BAExp to try and match them into nested structures (produces an AST)
	- Do this with parsing
```js
(define-struct baexp (op arg1 arg2) #:transparent)

// e.g. (parse '(+ 1 2)) => (make-baexp '+ 1 2)
(define (parse exp)
  (match exp
    ;; (op arg1 arg2)
    [(list op arg1 arg2) (make-baexp op (parse arg1) (parse arg2))]
    ;; number
    [num num] ;; match produce
    ))
```

**Abstract syntax tree:** captures the structure of a program/expression
- Each node is a function / argument to a function
- Other syntax (i.e. parentheses) → captured implicitly
	- *Note* → if you have a subtree it must have been a subexpression in parentheses

**Types of quotes:** 
- **Quote `'`:** a function that produces the argument unevaluated
	- I.e. `(list '+ 1 2) = '(+ 1 2)` → don’t evaluate the addition
- **Quasiquote (backtick):** like quote, but allows unquoting of subexpressions
- **Unquote `,`:** ignores the quoting if it appears in a quasiquoted expression
	- ![[Screenshot 2025-11-20 at 2.08.43 PM.png]] 
	- Unquote cancels out quasiquote (only expression it is connected to)
```
(define-struct baexp (op arg1 arg2) #:transparent)

;; e.g. (parse '(+ 1 2)) => (make-baexp '+ 1 2)
(define (parse exp)
  (match exp
    ;; (op arg1 arg2)
    [`(,op ,arg1 ,arg2) (make-baexp op (parse arg1) (parse arg2))]
    ;; number
    [num num] ;; match produce
    ))
```

**Lambda calculus parsing:** 
- Recall [[cs145 - Lazy Racket and Lambda Calculus|definition]] 
	- Must be a variable (`x`), application `(e1 e2)` or abstraction `(lambda (x) e)` 
- Can create 3 structures to store info for each of these
- **Steps:** 
	- *parsing, using match*
		- Like an AST:
			- Application is root node
			- Then it goes to abstraction / variable under it
				- And under variable is the actual values
```racket
(define-struct Var (id) #:transparent)
(define-struct App (fst snd) #:transparent)
(define-struct Abs (par bdy) #:transparent)

(define (parse sexp)
  (match sexp
    ;; Abs
    [`(lambda (,x) ,y) (Abs x (parse y))]
    [`(λ (,x) ,y) (Abs x (parse y))]
    ;; App
    [`(,x ,y) (App (parse x) (parse y))]
    ;; Var
    [x (Var x)]
    ))
``` 
- Interpretation and evaluation: (check A11)
	- *dealing with “outermost” interpreting* 
		- Interpret head
	- *substituting*
	- *dealing with “inner” interpreting* 
		- Just recurse by calling the actual interpreter (which then calls the outer interp repeatedly)
	- *combining everything together* 
- Example of substituting in body:
	- `(λx. (λy. y)) [x <- t]` 
		- Parameter = x
		- Body = λy. y
			- Splits into id & bdy2 (first and second y)
		- Exp = t
	- `(λx. (λy. x)) [x <- t]` 
		- `y` is not the same as `x` so substitute for the expression into the body 2
		- Get `λy. t` 
	- `(λx. (λx. x)) [x <- t]` 
		- Par x
		- Body λx.x
			- Id and bdy2 are both x
			- The inner id binds x
		- Exp t
		- `λx. x` 
			- The outer x gets removed
- Full example:
	- `(λx. ((λf. x) y) f)` 
		- `= (λx. ((λt. x) y)) f` 
		- `=> (λt. f) y` 
		- `=> f` 
	- *Note* → interpreter right now doesn’t do alpha equivalence
		- THIS IS THE HOMEWORK




# References

