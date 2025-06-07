2025-06-06 23:41

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - Keys

**Keys:** unique identifiers for all items in a React component (special type of prop)
- Allows it to only need to re-render some instead of all items in a component
- `<Component key={...} />` 
- Usually use a unique id if generating yourself
	- I.e. `crypto.randomUUID()` 
	- Can also use array index (map) → not recommended because it might change
- **NOTE:** keys should have some sort of pattern/consistency (no constant changing)
- ==Convert to an object from a list to properly generate id== 



# References

