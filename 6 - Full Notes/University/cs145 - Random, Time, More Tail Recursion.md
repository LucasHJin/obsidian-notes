2025-09-30 10:29

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Random, Time, More Tail Recursion

**Random:** generates a random integer r from 0 to n inclusive
- Not a function → not same output for every input
- *Pseudorandom* → follows a sequence of steps to generate these numbers (not completely random)
	- Based on timing → produce function with modulus and time
	- $r_{n+1}=(a*r_{n-1}+b) mod c$ 

**Timing:** `(time expr)` produces the amount of time required to evaluate the expression
- Need to import it → `(require racket/base)` 
	- **USE ONLY FOR TESTING ^^** → can’t submit for marmoset
- Produces `cpu time`, `real time`, `gc time` 
	- **CPU Time** → central processing unit
		- How much time the computation took (milliseconds)
	- **Real Time** → how much time from evaluation to seeing the result
	- **GC Time** → garbage collection time
		- Memory usage time (freeing up unused memory)
	- ^^ These happen simultaneously (parallel)

**Step vs Time:** 
- *Note* → number of steps is a good indicator of run time EXCEPT when there is hidden overhead
- I.e. tail vs non-tail recursive versions of sum to
	- Steps (n=100):
		- Non-tail → 604
		- Tail → 605
	- Actual Runtime (n=3 million):
		- Non-tail → 1.3 seconds
		- Tail → 0.1 seconds

**Call Stack:** 
- You take up space in memory as you recurse and function calls/returns get stacked on top of each other
- Tail recursion → no extra space in memory because it doesn’t need to remember values for any future operations
- ![[Untitled_Artwork 10.png]] 

*Note* → when constructing lists for testing (i.e. making big list)
- Using append of a larger list onto a single element list → MUCH SLOWER
	- Proportional to size of first list because you need to transfer over every element from first list to second
- Fastest to just use `cons` 
	- Rarely use append


# References

