2025-06-05 20:15

Status:


Tags:
[[cs]] 
[[ios]] 
[[mobile dev]] 


___________________________________________________________________________
# Swift - Collection Data Structures

**Array:** ordered collection of values (square brackets)
- Can have duplicates
- Mutable if declared with `var` 

**Dictionary:** key-value storage
- Keys need to be unique → values can be any type
- Unordered

**Set:** unordered set of unique values
- Like array but unordered and no duplicate (faster checking)

**Tuple:** ordered fixed size group of multiple values (round brackets)
- **ONLY ONE ALLOWED TO HAVE MIXED TYPES**
- Check with name or index
- Typically used with returning multiple values from a [[Swift - Functions and Closures|function]] 
```swift
let person = (name: "Alice", age: 30)
print(person.name) // Alice
```

# References
https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes/
