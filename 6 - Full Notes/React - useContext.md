2024-09-27 09:56

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - useContext

**UseContext:** allows you to share values between multiple levels of components without passing [[React - Props|props]] 
- I.e. nested components can all access value (like global) without passing props (like parameters/arguments) 
	- Each component is a file -> i.e. `ComponentA.jsx` 

**2 parts:** 
- **Provider component:** 
	- ![[Screenshot 2024-09-27 at 9.34.34 PM.png|400]] 
		- Name MyContext as `{state variable}Context` 
- **Consumer component:** 
	- ![[Screenshot 2024-09-27 at 9.34.48 PM.png|400]] 
	- Traverses up component tree to find nearest provider





# References

