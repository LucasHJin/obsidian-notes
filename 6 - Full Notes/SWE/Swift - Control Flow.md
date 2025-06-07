2025-06-05 18:56

Status:


Tags:
cs]]
[[ios]]
[[mobile dev]]


___________________________________________________________________________
# Swift - Control Flow

Touched on in [[Swift - Basic Syntax]] 

**Conditionals:**
- **`if` statement** 
	- Just like all other languages
		- Can have `if, else if, else` 
- **`switch` statement** 
	- Advanced form of if statement → must be exhaustive (cover all options)
	- Use `switch var {case: ... default: ...}` 
		- Provide a variable and match it to a value, ranges, tuples, enums (using ellipses)
	- Immediately breaks out of the statement after the first match
		- No falling through to next statement ([safer](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/controlflow/)) 
- **`guard` statement**
	- Exits a function, loop, or block if the condition ==is not met== 
		- Handles failures upfront
	- [[Swift - Basic Syntax|Reference]] 

**Loops:** 
- **`for in` loop**
	- Loops through collections, ranges, sequences (i.e. `1...5`)
	- Just like in Python
- **`while` loop**
	- Repeats code while a condition is satisfied
- **`repeat while` loop**
	- Same as a [[Javascript - Loops and Arrays|do while]] loop but different terms (executes at least once)
	- `repeat ... while condition` 


# References
https://www.programiz.com/swift-programming/for-in-loop 
