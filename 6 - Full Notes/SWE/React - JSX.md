2025-06-06 22:30

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - JSX

**JSX:** extends upon Javascript to allow you to write HTML style markup in javascript code
- Allows code in React to be compiled down to plain objects

**Rules:** 
- Can only return 1 root element (`<><\>` or `<div><\div>`) 
- Close all tags
- Use camel case for any attributes/modifiers

**Rendering techniques** (to render a list / conditional rendering)
- List of elements → just use map while adding a `key` to each element
- List of components → can pass into separate component where the list is then mapped out into a bunch of components
- Conditional:
	- **Ternary operator** → for single line boolean (`ternary ? true : false`)
	- `&&` **operator** → if first statement is true, second is rendered
		- Otherwise nothing happens
	- Can also use if/else + switch
 



# References

