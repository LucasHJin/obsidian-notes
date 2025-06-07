2025-06-05 20:24

Status:


Tags:
[[cs]] 
[[mobile dev]] 
[[ios]] 


___________________________________________________________________________
# Swift - Enums

**Enum:** a type that lets you define a group of related values in a type-safe way
- Can: 
	- Have associated values
	- Have raw values
	- Have methods
	- Conform to protocols
```swift
enum Direction {
    case north
    case south = 1
    case east
    case west
}
var travelDirection = Direction.north
travelDirection = .west
```
- Importance → 	Fixed set of related values
	- So it guarantees no random invalid states

TALK ABOUT SWITCH PATTERN MAKING

# References

