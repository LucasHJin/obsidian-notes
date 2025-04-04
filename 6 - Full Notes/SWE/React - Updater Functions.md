2024-09-26 13:35

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - Updater Functions

**Updater functions:** Method that allows for hooks like [[React - useState]] to update immediately instead of only after all hooks have been processed

**Common Naming Pattern:** 
1. ==Use the first letter of the state variable== 
	- I.e. for `count`
		- `setCount(c => c+1)`
1. ==Use descriptive naming== 
	- I.e. for `count` 
		- `setCount(prevCount => prevCount+1)` 


# References

