2025-11-18 14:17

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Big Picture of How Programs Work

**3 main groupings:** 
- Compiled
- Interpreted
- Hybrid

**Interpreted:** 
-  ![[Untitled_Artwork 20.png]]

**Compiled:** 
- ![[Untitled_Artwork 21.png]]

**Hybrid:** 
- ![[Untitled_Artwork 22.png]]

___

**Interpreters:** 
- Dr. Racket is an IDE
	- Racket is an interpreted language
	- Racket is also an interpreter

**REPL:** an interactive programming environment that allows users to input code and receive immediate feedback on its execution
- *Read (scanning)*
	- **Tokenizing:** grouping sequences of characters into tokens
	- Splits by whitespace (delimiter) normally
		- Also splits by brackets in Racket
	- **Lexical analysis:** want to know what keywords, variables, numbers, etc. look like (i.e. define, if, cond, lambda, etc.)
- *Evaluate*
	- **Abstract Syntax Tree (AST):** Transforms sequences of tokens into more meaningful structures
		- Traversing + simplifying AST –> produces value of expression/program
	- **Parsing / syntactic analysis:** groups tokens into more meaningful structures
		- Capture structure/form
	- `match`: abstract general cond
		- See [[cs145 - Building A λ-calculus Interpreter]] 
- *Print*
	- 
- *Loop*
	- 
![[Untitled_Artwork 23.png|400]] 



# References

