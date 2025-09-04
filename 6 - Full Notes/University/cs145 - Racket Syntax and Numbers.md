2025-09-04 10:00

Status:


Tags:
[[cs]] 
[[uni]] 
[[cs145]] 


_______
# cs145 - Racket Syntax and Numbers

**Tool:** 
- [[cs145 - DrRacket]] 

**Racket** → a functional programming language (not imperative – i.e. C/Python)
- Dialect of Scheme (descendant of LISP)
- Similar to Excel (i.e. when you calculate the functions in the cells)
	- Take set of data and then apply functions to this and do something with the result
- Uses *Prefix Notation* (normal → *Infix Notation*) 
	- Many brackets

**Prefix notation:** the operator/function goes before the operand/arguments
- Function goes before the arguments
	- I.e. `(+ 42 8) = 50` 
	- I.e. `(+ (+ 42 10) (- 18 5)) = 65` 
- **Syntax** for all function operations: 
	- `(fn arg1 arg2 ... argn)` 
	- Applies the function to all arguments

**Arithmetic operators:** 
- `+`, `-`, `/`, `*`, `sqrt`, `quotient` (integer division), `remainder`, `modulo`, `add1`, `sub1`, `expt`, `log`, `max`, `min` 
	- `x/y` gives same value but it’s a way of writing a rational number (not a function)
	- `modulo` and `remainder` are different for negative
		- Modulo gives same sign as the modulus (second value)
		- Remainder gives same sign as the divisor (first value)
		- ![[Screenshot 2025-09-04 at 10.51.11 AM.png|250]] 
	- `add1`, `sub1` is useful for recursion (it’s like `+=`)
	- `max`, `min` → gives max/min out of all arguments
	- `log` → is base e (gives inexact)
		- Can add 2 values to change the base

**Defining constants:** 
- `(define x 10)` → same as $x=10$ 
	- *Syntactic sugar:* the difference between the two above expressions
	- `define` → doesn’t return an output (not technically a function) 
		- Evaluates expression and then assigns output value to the constant
- *Note* → can’t redefine constants
	- ==No variables in racket== 

**Defining functions:** 
- `(define (f x) (+ x x))` → same as $f(x)=x+x$ 
	- `define` and $=$ are equivalent, just changing structure, not the content
- Just call in the interactions terminal by subbing for x
	- Doesn’t have to be a value (can be variable/function) 
- Can define more functions

**Stepping:** 
- Racket expressions are evaluated until they become a value / error (**step button**)
	- Done in steps
	- **Small substitution:** For ==built in== functions → if arguments are all **values**, the answer is given in one step
		- Otherwise → does it in multiple steps
	- **Big substitution:** For ==user== functions → if all arguments are **values**, produces the body of the function with values subbed in
		- I.e. will get the actual value on second step
		- `(f 7) -> (+ 7 7) -> 14` 
- Evaluate either inner most (nested) or left most expression first

**Technical details:** 
- `;;` → to add comments
- Spaces/newlines don’t matter (don’t impact function/argument)
	- Racket indents nicely
- Multiple arguments → use parentheses each time
- [Documentation](https://docs.racket-lang.org/) 
	- *Note* → search for the proper “beginner” section

***Notes:*** 
- You can write any integer in Racket (no size limit/overflow + pos or neg)
- Stores rational numbers exactly
	- Overlines for repeating numbers → i.e. ![[Screenshot 2025-09-04 at 10.38.57 AM.png|100]]  
	- ==Not approximated → exact== (allows us to get exact values from things like 3 times 1/3)
- Inexact numbers → denoted by `#i` 
	- Means there is no fraction that can represent (it’s irrational)
	- I.e. ![[Screenshot 2025-09-04 at 10.42.55 AM.png|300]] 
	- Means that once inexact, it’s hard to convert back to exact


# References
https://student.cs.uwaterloo.ca/~cs145/handouts/slides/lec01.pdf
