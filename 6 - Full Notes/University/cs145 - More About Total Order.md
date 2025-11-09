2025-11-07 10:41

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - More About Total Order

*Note* → `string-ci<=?` compares without caring about capitalization
- Empty string is min
- `lambda` is max

`os-op` → folds `to-op` onto everything on the set
- I.e. if `to-op` is addition
	- `(os-op (list 1 3 7)) = 11` 
	- Op is associative so that order doesn’t matter (makes it O(1))




# References

