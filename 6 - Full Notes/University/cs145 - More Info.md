2025-10-10 10:38

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - More Info

You can do almost anything with lambda in Racket
- Can implement struct with lambda
- Storing local variables with lambda:
	- use `lambda (index)` and then it replaces all instances of index with the desired value
		- Wrap function body with lambda
	- ==DON’T ACTUALLY DO THIS== 

**Apply:** applies a function to a list
- `(apply f (list a b)) => (f a b)` 
- Expects n values from list to apply to the function

**Mutual tail recursion:** two functions mutually call each other’s functions
- Instead of this → can just return info required to call the second function (then a third function does the calling) (makes them fully tail recursive)
	- Pass the function ref (not function call)

**CHALLENGE:** take a recursive implementation for tree count
- Make it tail recursive with zippers + trampoline

# References

