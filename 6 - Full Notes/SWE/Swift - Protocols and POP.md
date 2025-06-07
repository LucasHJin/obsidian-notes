2025-06-07 13:53

Status:


Tags:
[[cs]]
[[ios]]
[[mobile dev]]


___________________________________________________________________________
# Swift - Protocols and POP

**Protocol:** a blueprint for methods, properties, or behaviors that a datatype must implement
- Doesn’t give any implementation of the functions
- Just says that any type of this protocol must have these functions
- **Benefits:** 
	- Allows you to abstract general behavior
	- Is reusable
	- Separates what from how
- **Writing protocols:** 
	- Must have `{ get }` or `{ get set }` → defines if only need read behavior or also write
		- Only `var` if get + set

**Protocol Oriented Programming (POP):** Model behavior with protocols first, not inheritance
- No defining one big class → define small reusable behaviors and mix and match them between different types (instead of subclassing)

*Note:* Can pass these protocols into functions
- Allows it to take any type ([[Swift - Structs and Classes|struct or class]]) that conforms to the protocol

**Example:** 
```swift
// Defining protocols
protocol Identifiable {
    var id: String { get }
}
protocol Nameable {
    var name: String { get }
}

// Conforming to 1 
struct User: Identifiable {
    var id: String
}

// Conforming to multiple
struct Pet: Identifiable, Nameable {
    var id: String
    var name: String
}

// Protocol in function
func displayID(thing: Identifiable) {
    print("ID is \(thing.id)")
}
```

| Protocol                  | Description                                                                    |
| ------------------------- | ------------------------------------------------------------------------------ |
| `Codable`                 | Encode/decode types to/from JSON or other formats (`Encodable` + `Decodable`). |
| `Encodable`               | Enables a type to be encoded (e.g., to JSON).                                  |
| `Decodable`               | Enables a type to be decoded (e.g., from JSON).                                |
| `Equatable`               | Enables comparison using double equals and not equals.                         |
| `Hashable`                | Allows use in `Set` and as `Dictionary` keys.                                  |
| `Comparable`              | Enables sorting and comparison (less than, greater than, etc.).                |
| `Identifiable`            | Requires a unique `id` — used often in SwiftUI lists.                          |
| `CustomStringConvertible` | Provides a custom `description` string for `print()` and debugging.            |
| `CaseIterable`            | Provides `.allCases` for enums to access all possible cases.                   |
| `Error`                   | Used to define custom errors for use with `throw`, `try`, and `catch`.         |
| `OptionSet`               | Represents option flags with bitmask behavior.                                 |
| `NSCopying`               | Allows making copies of class instances.                                       |
| `Sequence`                | Enables iteration in `for-in` loops.                                           |
| `Collection`              | Adds indexing, count, and other features to `Sequence`.                        |
| `RandomAccessCollection`  | Enables fast index-based access (like arrays).                                 |
| `View` (SwiftUI)          | Base protocol for all SwiftUI views.                                           |
| `ObservableObject`        | Used in SwiftUI to trigger view updates when data changes.                     |

# References
https://www.programiz.com/swift-programming/protocols
