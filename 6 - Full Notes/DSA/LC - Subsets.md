---
difficulty: medium
review: true
---
2025-11-30 13:36

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n * (2^n))
- Because you have 2 choices for every single idx in the input array
	- Either include it or don’t → 2^n
- There is the n because creating the subsets is n/2 on avg
**Space complexity:** O(n)
_______
# LC - Subsets

**Preliminary notes:** 
- Given an array, you want to make all possible sub arrays of it and return them in one big list
	- Use recursion for this + [[Backtracking explained|backtracking]] 
	- Any combination (order doesn’t matter)
- Has no constraints → no case where it violates

*REMEMBER:* 
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

**Finished notes:** 
- For each number in the array → you can either add it or not
	- 2 options result from this → i.e. either add a 3 or don’t
	- Can backtrack after adding 3 case to do not adding 3 case
- *How to manage using state:* 
	- `index` → track which index we are currently considering
	- `path` → current subset (will be completed once index reaches length of list)
	- **NOTE:** 
		- For answer, need to append copy of path → `path[:]` 
		- So that you don’t pass a reference (pass a new independent list)
- Use append and pop
	- Call backtrack with and without added value
- *NOTE* → could also use a bitmask approach

# References

