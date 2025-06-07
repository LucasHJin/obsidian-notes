2025-06-07 14:29

Status:


Tags:
[[cs]] 
[[ios]] 
[[mobile dev]] 


___________________________________________________________________________
# Swift - Generics and Extensions

**Generic:** allows you to write functions, structs, enums, classes that work with any type
```swift 
// Generic function
func functionName<T>(parameters using T) { ... }
	// Add inout if you want to be able to modify

// Generic struct/class
struct Name<TypeParameter> { ... }

// Generic constraint
func functionName<T: Protocol>(...) { ... }
```

**Extensions:** let you add new methods, properties, or initializers to existing types
- Helpful for organization and better functionality
```swift
extension String {
    func reversedText() -> String {
        return String(self.reversed())
    }
}
```


# References

