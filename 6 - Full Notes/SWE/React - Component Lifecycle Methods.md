2025-06-23 15:03

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# React - Component Lifecycle Methods

Three stages in a component lifecycle (mounting, updating, unmounting)
- [[React - Lifecycles]]  
	- Each has a method for [[React - Class Based Components|class components]] 

`render` → runs on mount and update of a component
- Is required
- Is pure:
	- Doesn’t modify component states, returns the same thing each time (given same inputs), doesn’t directly interact with browser

`componentDidMount()` 
- Run after mounted (inserted into DOM tree) 
- Good for fetching data/API calls

`componentDidUpdate()` 
- Runs after a component rerender
	- Update anything that will be changed (i.e. states)

`componentWillUnmount()` 
- Use to perform cleanup actions
	- I.e. cancel network actions, cleanup timers, etc.

**UseEffect** does all of the above for functional components
- [[React - useEffect]] 




# References

