2025-06-05 20:24

Status:


Tags:
[[cs]] 
[[ios]] 
[[mobile dev]] 


___________________________________________________________________________
# Swift - Structs and Classes

The main two ways to make custom data types
- `struct` → **value type** (copies any passed values)
	- Is lightweight, no inheritance from other structs
		- If you want to change a value, append `mutating` (immutable by default in instance values)
	- Useful everywhere
		- SwiftUI views, small models
- `class` → **reference type** (shares memory with any passed values, i.e. changing those values changes its memory as well)
	- More flexible and can inherit from other classes
	- Used for object identity (model objects, view controllers, etc.) 
		- Complex objects

*Note:* Both can define an initializer (mandatory for class)
```swift
struct Person {
    var name: String
    var age: Int

    init(name: String) {
        self.name = name
        self.age = 0
    }
}
```

**General use cases:** 
- Use struct if you need to represent data to read it
- Use class if you will constantly change properties / if you want to share state accross multiple files

# References
https://developer.apple.com/documentation/swift/choosing-between-structures-and-classes

https://www.reddit.com/r/swift/comments/ymh2c8/appropriate_uses_of_structs_vs_classes/ 