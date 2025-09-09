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
- **Expression:** when it’s not a single value

***Data types:*** 
- You can write any integer in Racket (no size limit/overflow + pos or neg)
- Stores *rational numbers* exactly
	- Overlines for repeating numbers → i.e. ![[Screenshot 2025-09-04 at 10.38.57 AM.png|100]]  
	- ==Not approximated → exact== (allows us to get exact values from things like 3 times 1/3)
- *Inexact numbers* → denoted by `#i` 
	- Means there is no fraction that can represent (it’s irrational)
	- I.e. ![[Screenshot 2025-09-04 at 10.42.55 AM.png|300]] 
	- Means that once inexact, it’s hard to convert back to exact
- *Complex numbers* → do exist in racket as well
- *Symbols* → use a `'` at the front of the symbol
	- Are technically values (no spaces)
	- Indicate a small set of potential values
- *Strings* → use `""` around them
	- Note → strings can have whatever characters you want in them
	- Store larger universe of possibilities
- *Booleans* → true or false

**Boolean functions:** 
- `<, <=, >, >=, =` → comparison functions for numbers
	- = sign is only for numbers
- *Logical operators* → `and`, `or`, `not` 
	- `and` → [[m135 - Conjunction and Disjunction|conjunctive]] (all values need to be true)
	- `or` → [[m135 - Conjunction and Disjunction|disjunctive]] (at least one value needs to be true)
	- **NOTE:** → not all arguments are evaluated for `and` and `or` 
		- I.e. `(and true false (> (/ 0 0) 3))` → will evaluate false because it already sees the `false` at the second step
		- *short circuit* logic
- *Predicates* → tell us something about argument (produce boolean values)
	- `string?`, `number?`, `symbol?`, `symbol=?`, `zero?`, `integer?` 
	- I.e. `(number? 6)` is true because it is a number
	- `symbol=?` → used to compare equality of two symbols

**Conditional operators:** 
- If statement → `(if test true-exprs false-exprs)` 
	- Short circuits again → doesn’t go through everything
	- *Note* → there is no `elif` 
		- Nesting loops gets complicated
- Cond statement → like a switch in [[Swift explained|Swift]] 
```js
(cond (question-expression answer-expression)
      ...
      (else answer-expression))
```
- Also short circuits → doesn’t go past answer expression if the question is true
	- Doesn’t evaluate the answer expression if it’s false
	- `else` → guarantees that something is always evaluated

**Syntax:** means structure/form
- All racket functions have the syntax: `(<fn-name> <arg1> ... <argN>)` 
- **Syntax errors:** always going to be because it doesn’t look like the above
**Semantics:** means meaning
- Can have right syntax but wrong meaning 
- [Semantic rules](https://student.cs.uwaterloo.ca/~cs145/handouts/slides/lec02.pdf) (slides 5, 6)
- *Note* → `(and) => true`, `(or) => false` 
	- This is not what the stepper does in racket
		- No more args → they were all true or not a single true encountered
	- ==BUT → THIS IS ON QUIZ 1 (DO THIS STEP)== 


# References
https://student.cs.uwaterloo.ca/~cs145/handouts/slides/lec01.pdf
