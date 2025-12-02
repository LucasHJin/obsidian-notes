2025-08-16 17:47

Status:


Tags:
[[dsa]] 
[[lc]] 


_______
# Backtracking explained

Recursive problem solving technique that explores all configs of a solution but efficiently backs up when it realizes the path won’t work
- I.e. DFS but able to reverse a choice
- **General pattern:** 
	- ![[Screenshot 2025-08-16 at 5.49.48 PM.png]] 
	- If answer is found → return a copy of it
	- Else → go through all other possible paths
		- First get rid of impossible choices and then commit to the choice
		- Repeat process and then undo the decisions made (so not stuck on first path forever)
- Like a maze → if dead end, go back
	- Different from recursion → manages using state and recursion

**Template:** 
- Visualize as a decision tree
	- Each level of tree represents decision point, each branch is an option you can take
	- [[LC - Subsets]] 
```python
def backtrack(params):
    if base_case_condition:
        save_result
        return

    for choice in choices:
        if violates_constraints:
            continue

        make_choice
        backtrack(updated_params)
        undo_choice  # Backtracking Step
```


___

**Useful for:** 
- Combinations, permutations, etc.
- Building up a partial solution
- Want all possible solutions
	- I.e. “try all the ways to do x but only return the valid ones”
- Need to discard bad paths early 
- **Specific problems:** 
	- Sudoku solvers
	- Word searchers
	- Permutation/combination problems (i.e. N queens)

**Examples:** 
- *Word search* → pruning is the check to see if the letter matches the grid (return false if it is not the case)
	- Check base case → is it last letter and it matches
	- Mark current cell with an asterisk (to not reuse in the current path) → for each direction, check if its inside board boundaries and recursively call dfs
		- Memory optimized → don’t need an entire 2D visited list
	- If return true → valid path
	- AFTER EXPLORING → reset current cell back to original letter
- ![[Screenshot 2025-08-16 at 5.55.14 PM.png]] 


# References

