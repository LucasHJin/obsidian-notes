2024-09-27 09:56

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - useRef

**UseReference:** Allows a component to remember a value without re-rendering
- Similar to [[React - useState]] but no re-render

**Usecases:** 
- Accessing/interacting with DOM elements
- Handling focus, animations and transitions
- Managing timers and interavls

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

