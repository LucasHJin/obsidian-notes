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
- Arguments are passed unevaluated (only evaluated when necessary)
- All occurrences of the same expression are evaluated simultaneously 

___
**Model of computation:** a set of simple rules that can express any computation that can be performed in any programming language (i.e. Turing Machine)
- **Lambda-calculus** is an example of a MoC
- *Note* → models of computation should be equivalent
	- Any problem that can be solved in any programming language can be solved in ALL programming languages
	- *Note* → not all problems are solvable by computer

**Lambda calculus:** a set of rules for forming (syntax) and evaluating (semantics) lambda expressions
- **Lambda-expressions:** 
	- A variable → `x, y, a, ...` 
		- I.e. `'x "y" a` 
	- An application → `(e1 e2)` where e1 and e2 are lambda expressions
		- I.e. `(abs 4)` 
	- An abstraction → `(λx.e)` where e is a lambda expression and x is a variable
		- I.e. `(lambda (x) e)`
- *Note* → expressions are left associative (just like arithmetic operators)
	- Omit parentheses when there is no ambiguity 
		- (use them to override order of operations)
	- Shorthand notation:
		- `e = (e)` 
		- `λx.e = (λx.e)` 
		- `e1 e2 e3 = (e1 e2) e3` 
		- `λx.e1 e2 = λx.(e1 e2)` 
- **Free variables:** Let `FV[e]` denote the set of free variables of a λ-expression `e`
	- If `e` is a variable `x` then `FV[e]={x}` 
	- If `e` is an application of `e1 e2` then `FV[e1 e2]=FV[e1] U FV[e2]` 
	- If `e` is an abstraction `λx.e'` then `FV[λx.e']=FV[e']\{x}` 
	- Basically → `λx.x` has x being bound while `λx.y` has y being free (is parameter related to body)
- **Substitution:** uses notation `e1 [x <- e2]` (there are other forms of notation)
	- Replace all instances of FREE VARIABLE x in e1 with e2
	- **Formal definition:**
		- For a variable `x`, `x [x <- e] = e` 
		- For a variable `y`, `y [x <- e] = y` (sub has no effect)
		- `(e2 e3) [x <- e1] = (e2[x <- e1] e3[x <- e1])` 
		- `(λx.e2)[x <- e1] = (λx.e2)` (because x is not free in e2 → it is bound)
		- `(λy.e2)[x <- e1] = λy.(e2 [x <- e1])` given `x≠y` and `y not in FV[e1]` (criteria prevents capture)
- **alpha-equivalence:** `(λx.e1)` and `(λy.e2)` are a-equivalent if `y not in FV[e1]` and `e2 = e1[x <- y]`  where y is not a free variable in e1 such that you can substitute y for x in e1
	- Denoted with `≡_α` (just use equal for simplicity in notes)
	- I.e. `λx.x = λy.y` 
		- `e1[x<-y] = x[x<-y] = y = e2` 
	- *Note about capture:* 
		- Suppose we didn’t insist the y is not a free variable in `FV[e1]` 
		- `(λy.x)[x<-y] = λy.(x[x<-y]) = λy.y` (not same meanings)
			- Give me a y and i’ll give you x versus give me a y and i’ll give you y
			- Normally → can’t substitute y into x because it’s a free variable in e1
		- a-equivalence allows us to make fresh variables (can rename parameters to avoid conflicts)
		- Need free variables for next type of reduction
- **beta-reduction:** `(λx.e1) e2` can be beta-reduced to `e1[x<-e2]` (apply an abstraction with an argument) (substitution must follow rule 5)
	- Denoted with `⇒β` (use => for simplicity in notes)
	- I.e. `(λx.f x) y => f y`
		- I.e. in racket → `((λ x (f x)) y) => (f y)` 
	- Need the restriction because we want x to disappear
- **Reducible expression (redex):** if it can be beta-reduced with/without the help of alpha-equivalence
	- Not every lambda-expression is a redex (some can’t be further reduced)
	- If e1 reducible to e2: `e1 =>_{αβ} e2` 
	- Examples:
		- `(λx.a x b) (λy.y) => a (λy.y) b` 
			- e1 is `a x b` e2 is `λy.y` (replace all instaces of x)
		- `(λx.a x b) (λy.x) = (λq.a q b) (λy.x) => a (λy.x) b`  
			- e1 is `a x b` e2 is `λy.x` 
- **Determining reducibility:** 
	- If `e=x` is it not a redex (fully reduced lambda expression)
	- If `e=e1 e2` (i.e. an application) and both e1 and e2 are redexs, then we can reduce:
		- `e1` first
			- I.e. `e1 e2 => e3 e2` 
		- `e2` first
			- I.e. `e1 e2 => e1 e4` 
		- first apply `(e1 e2)` and then reduce
			- I.e. if `e1 = λx...` then `e1 e2 => e1'[x<-e2]` 
- **Fully reduced** → if no redexes
	- It is undecideable if a given lambda has a fully reduced form
	- If we do know → use **Normal Order Evaluation** 
- **Normal Order Evaluation:** given more than 1 redex to reduce, always pick the leftmost redex
	- I.e. `(λx.x x) ((λy.y) q)` → 2 redexes (entire expression and `((λy.y) q)`)
		- `=>B λx.x x [x <- (λy.y)q]` (intermediate step - not seen)
		- `=>B ((λy.y) q)((λy.y) q)` 
		- `=>B q ((λy.y) q)` 
		- `=>B q q` (fully reduced)
- **Applicative Order Evaluation:** given more than 1 redex to reduce, always reduce the inner-most redex first
	- I.e. `(λx.x x) ((λy.y) q)` 
		- `y[y<-q] =>B (λx.x x) q` 
		- `x x [x<-q] =>B q q` (fully reduced)
	- **WILL NOT** always find the fully reduced form
		- I.e. `(λx.y) ((λx.x x) (λx.x x))` 
			- `=>B (λx.y) ((λx.x x) (λx.x x))` (will run infinitely on the inside one because it doesn’t have a redex)
				-  `x x[x<-λx.x x] =>B (λx.x x) (λx.x x)` 
		- *Normal order:* 
			- `=>B y` (fully reduced)
- *NOTE* → you don’t need to show the square bracket part (substitution) unless asked
	- Can just show the result of beta reduction

# References

