2024-08-21 13:46

Status:


Tags:
[[cp]]
[[cs]]
[[dp]]


___________________________________________________________________________
# Prefix DP explained

**DP state:** a way to represent a subproblem or a smaller piece of the overall problem that you're trying to solve
- encapsulates all the information needed to solve that specific subproblem
- I.e. `dp[i]` 

**Prefix DP:** Building the solution by progressively adding elements from the start up to a certain point
- Each state represents a solution for a portion of the sequence starting from the beginning
	- Just add on recursively `dp[i-1]` to get `dp[i]` 
- (Consider each prefix (each individual state))

Relates to → [[Prefix sum explained]] 


# References

