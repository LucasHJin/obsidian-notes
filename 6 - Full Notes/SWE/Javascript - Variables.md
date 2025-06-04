2025-06-02 08:47

Status:


Tags:
[[cs]]
[[webdev]] 


___________________________________________________________________________
# Javascript - Variables

Method of storing data
- **Declaration:** “announces” that the variable is existing now
- **Initialization:** gives the variable a value

**How to declare a variable:**
- Use `let` to make a mutable variable (changeable)
	- `var` also exists but it has been mostly replaced (**differences below**)
		- It is global/function scoped instead of just in a code block
		- It can be redeclared
		- It can be declared below its use
			- Declarations are processed at function start
- Use `const` to make an immutable variable (unchangeable, throws an error)

**Naming:** 
- For variables → use **camelCase** 
- For constants → use all upper case and underscore

**Operators:** 
- Loose equality (2 equal signs) → compares only value (after converting a common type)
	- Also exists `!=`
- Strict equality (3 equal signs) → compares both value and type
	- **Use this ^^** 
	- Also exists `!==` 

# References
https://javascript.info/variables#variable-naming 
