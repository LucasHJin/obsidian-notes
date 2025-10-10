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




# References

