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

**Associated values:** allow each case to store data of any type
- Gives details which can carry extra data

**Switch and Pattern matching:** 
- Links to [[Swift - Control Flow]] 
- Allows you to access the pattern of a case in an enum and pull data out of it to use it

**Example:**
```swift
enum Result {
    case success(data: String)
    case failure(error: String)
}

let result = Result.success(data: "File loaded")

switch result {
case .success(let data):
    print("Success: \(data)")
case .failure(let error):
    print("Error: \(error)")
}
```
- `.success()` matches the case
- `let data` pulls out data from inside the enum to be used
	- Can also add `where` clauses after this to have further conditions

# References

