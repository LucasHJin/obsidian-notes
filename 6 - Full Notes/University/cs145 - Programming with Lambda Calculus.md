2025-11-06 10:41

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Programming with Lambda Calculus

**To know:**
- [[cs145 - Lazy Racket and Lambda Calculus]] 

**Comparing:** easy to convert from lambda calculus to Racket
- ![[Untitled_Artwork 12.png|400]] 

**Computation:** 
- **Racket:** compute by repeatedly substituting expressions, based on semantic rules, until we get a value (can’t substitute anymore)
- **Lambda calculus:** compute by repeatedly applying a-equivalence or b-reductions to a lambda expression until there are no more redexes (fully reduced) 
- **Ex:** checking prime
	- Write a lambda calculus expression → `λn. λt. λf. ...` 
	- Apply a-equivalneces and b-reductions → `=>ab ...` 
	- At the end we have one variable:
		- `y` → indicates yes
		- `n` → indicates no

 **Redexes and Reduction strategies:** 
 - Steps:
	- Find a redex (`(λx.e1) e2`)
	- Apply (optionally) a-equivalence and then b-reduction
	- Repeat
- Sometimes → redex will not terminate (bad choice of reductions or no educed form - i.e. picking applicative order)
	- If there is a fully reduced form, it is **unique** (would get there in the end no matter what)
- **[[cs145 - Lazy Racket and Lambda Calculus|Normal order evaluation:]]** reduce the first redex found (left to right)
	- Evaluates the function before the arguments → guaranteed to find reduced form if it exists
	- **Call-by-name** → the method of implementing normal order evaluation
		- I.e. `(define (double t) (+ t t))` 
		- `(double (+ 1 2)) => (+ (+ 1 2) (+ 1 2)) => (+ 3 (+ 1 2)) => (+ 3 3) => 6` 
		- Consider it as a weird name (random thing you are given)
			- Just get the function with those parameters substituted in
- **Applicative order evaluation:** reduce the leftmost-innermost redex (keep repeating innermost until you get a tie and then do innermost)
	- I.e. `(λx.x) ((λy.y) z) => (λx.x) z => z` 
		- This is how racket evaluates
	- Exponentially faster than NOE
		- Simplifies things before plugging in as parameter so don’t need to evaluate multiple instances later on
		- Doesn’t aways find reduced form
	- **Call-by-value** → a possible method of implementing applicative order evaluation
		- I.e. `(double (+ 1 2)) => (double 3) => (+ 3 3) => 6`
- **Lazy Evaluation:** requires annotated (labelled) lambda expressions
	- Idea:
		- Replace each identical lambda-expression with a symbol (exact same symbol)
		- If any of the (equivalent) lambda expressions are evaluated, replace the symbol with evaluated result across the board
	- Strategy has the benefits of normal order without the longer running time
	- **Call-by-need** → Lazy Racket uses this (more overhead)

**Converting:** square brackets are shortform for saying the lambda calculus symbol of the Racket expression R is … (applying lambda calculus conversion)
- ![[Untitled_Artwork 13.png|400]] 
- ![[Untitled_Artwork 14.png|400]] 
	- *Note* → only defined for one parameter at a time
- ![[Untitled_Artwork 15.png|400]] 
- ![[Untitled_Artwork 16 1.png|400]] 
- ![[Untitled_Artwork 17.png|400]] 
- ![[Untitled_Artwork 18.png|400]] 
- *Note* → from this, you have:
	- Booleans, a data structure, selector functions, and a predicate
	- Can implement `and, or, cond` with `if` 


 



# References

