2024-08-21 13:46

Status:


Tags:
[[cp]]
[[cs]]
[[dp]]


___________________________________________________________________________
# Interval DP explained

**DP state:** a way to represent a subproblem or a smaller piece of the overall problem that you're trying to solve
- encapsulates all the information needed to solve that specific subproblem
- I.e. `dp[i]` 

**Interval DP:** Building the solution by considering **all possible subarrays or intervals** within the sequence
- Each state represents a solution for a specific interval between any two indices 
	- I.e. `dp[i][j]` is the state/solution from index `i` to `j` inclusive
- Useful for problems where the solution depends on combining smaller intervals
	- I.e. Parsing expressions
	- Matrix chain multiplication
	- Game strategies



# References
https://algo.monster/problems/dp_interval_intro
