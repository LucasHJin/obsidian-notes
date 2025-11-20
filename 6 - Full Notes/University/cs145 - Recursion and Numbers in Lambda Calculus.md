2025-11-11 14:03

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Recursion and Numbers in Lambda Calculus

*Note* → when local creates fresh names to avoid globally defined x, Racket worries about capture
- Need to apply alpha equivalence (unique names)
- Function replaces = beta reduction

*TO KNOW* → Lambda calculus has no named functions
- So you can’t do explicit recursion
- **Solution:** 
	- 1. Provide a function that it can use to call itself repeatedly (because you passed it as a parameter) → not explicitly recursive (use lambda)
		- `self` represents the function → i.e. `(fxn fxn)` 
	- 2. Can also make it only take that function and nothing else ([[cs145 - Lazy Racket and Lambda Calculus|curried form]]) 
		- Pass list to and-list-curry
	- 3. Can perform a beta reduction (replace `and-curry-helper` with the function bodies)

**Abstraction for lambda calculus recursion** → so that you don’t have to manually change the function
- Can just give any function and it is abstracted away
```
(define abstract-curry-no-helper
	(λ(f)
		((λ(self) (f (self self)))
		 (λ(self) (f (self self))))))
```
- Pass function as f
	- f takes 1 parameter → self
	- Expects a function that takes a function and calls the function back on itself

**Y-combinator:** a lambda calculus expression that allows you to do recursion
- `Y = λf. (λx. (f (x x)) (λx. (f (x x ))))` 
	- This is “Abstract No Curry Helper”
	- **Fixed point combinator:** a function such that the output value is the same as the input
		- `f(p)=p` 
		- Is the line `y=x` 
		- Want to find the points of function `g` that intersect y=x
- Example:
	- `Y g = λf. (λx. (f (x x)) λx. (f (x x))) g` 
		- `=> λx. (g (x x)) λx. (g (x x))` 
		- `=> g ((λx. g (x x)) (λx. g (x x)))` 
		- `=> g (Y g)` 
- ANSWER TO ASSIGNMENT 10 ^^^
	- You pass a function to f so that it’s repeatedly call (and just reference that function call)

**Natural numbers:** can think of them as abstraction / ADT with the following operations:
- `add1, +, -, *, sqr, etc.` 
- 3 possible implementations (because they don’t exist in pure lambda calculus):
	- Church numerals
	- Unary lists
	- Binary lists

**Church numerals:** number is just the number of times you apply a function f to x (*note* → not for assignment 10)
- `0 = λf. λx. x` 
- `1 = λf. λx. (f x)` 
- `2 = λf. λx. (f (f x))` 
- *Add 1*
	- `successor n = λn. λf. λx. f (n f x)` 
	- Take number n and apply function one more time (add1)
- *Addition* 
	- `plus n m = m+n = f^(m+n) = f^(m)f^(n)`
		- `= λm. λn. λf. λx. (m f (n f x))`
	- Apply the function m+n times on x
- *Multiplication* (repeated addition)
	- *Exponentiation* (repeated multiplication)

**Unary list:** like counting tick marks (represent using trues in a list)
- `0 = [empty]` 
- `1 = [cons] [true] [empty]` (lambda calc expression for cons, true, empty)
- `n = [cons] [true] [n-1]` 
- `add1 = (λ(x) (cons True x))` 
- `sub1 = [rest]` 
- `a+b = (a-1) + (b+1) = ... = 0 + (b+a)`
	- Keep on increasing + decreasing until a reaches 0 and b is then a+b
- `a*b = (a-1)*b + b = ... = 0*b + (a*b)` 
	- But this is O(n^2) 

**Binary list:** 
- `0 = [empty]` 
- `1 = [cons] [true] [empty]` 
	- `1_2 = 1` 
- `2 = [cons] [false] [cons] [true] [empty]` 
	- `10_2 = 2` 
	- Have `b^1, b^2, b^3...` columns → in this case b is 2
- `3 = [cons] [true] [cons] [true] [empty]` 
- `2n = [cons] [false] [n]` 
	- **Backwards binary representation:** false is at the start so it’s easier to cons values on (easy to put on at start of a list)
		- Shift base over 1 position
		- And you read from left to right (in reverse)

**Karatsuba Algorithm For Multiplication:** for multiplying 2 *n*-digit base-*B* numbers
- ==Useful for A10C== (using binary list)
- Pick an m < n
- `x = x_1 * B^m + x_0`, `y = y_1 * B^m + y_0` 
- `xy = x_1y_1B^(2m) + (x_1y_0+x_0y_1)B^m + x_0y_0` 
	- 4 multiplications to do just in the coefficients (call the coefficients `z2, z1, z0`)
- *Observation*: 
	- `z_3 = (x_1 + x_0)(y_1 + y_0) = x_1y_1 + x_0y_1 + x_1y_0 + x_0y_0` 
	- `z_1 = (x_1+x_0)(y_1+y_0)-x_1y_1-x_0y_0 = z_3 - z_2 - z_0` 
		- Only 3 multiplications → from `O(n^2)` to `O(n^(log_2 3))` 

# References

