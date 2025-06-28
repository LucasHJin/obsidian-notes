2024-09-27 09:56

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - useRef

**useRef:** Allows a component to remember a value without re-rendering
- Similar to [[React - useState]] but no re-render
- For when you want a component to remember info without refreshing
	- Value will not be destroyed each re-render (persists through lifecycle)
- *Note:* Change the `.current` property to update the value inside the ref
	- BUT → Do not write or read ref.current during rendering ([only in event handlers or effects](https://react.dev/reference/react/useRef)) 

**Usecases:** 
- Accessing/interacting with DOM elements
	- Can set a reference to a specific button and then focus on it 
	- **Note** → only use for non-destructive DOM operations
	- React commits to DOM instead of manual change (main point of the library)
- Handling focus, animations and transitions
- Managing timers and interavls
- Performing imperative actions

**How:** 
- Creating
	- `const ref = useRef(0)` -> returns 1 property (object of current)
	- Name normally `{element}Ref` 
- Incrementing value without re-render
	- `ref.current = ref.current + 1`
- Take object from inputRef -> access current property and focus on element
	- (makes it highlighted/selected)
	- `inputRef.current.focus();` 
- I.e. will change which is selected but only re-render once
- ![[Screenshot 2024-09-27 at 9.57.14 PM.png|450]] 
 





# References

