2025-06-05 18:40

Status:


Tags:
[[cs]]
[[ios]]
[[mobile dev]]



___________________________________________________________________________
# Swift - Functions and Closures

**Function:** ==need to declare types of parameters and return value== 
```swift
func greet(name: String) -> String {
    return "Hello, \(name)!"
}
```
- When you call, you have to put the variable in front of argument
	- `let message = greet(name: "Lucas")` 
	- Unless you have an underscore in front of the parameter in the function
- You can return multiple values (associate each with an attribute of the function)
	- I.e. `result.a, result.b`
- Useful for logic

**Closure:** anonymous function (similar to lambda)
- Don’t need to write `func` and can assign to variable
	- Still need to have parameters and return value types
- Format: `{... in ...}` 
```swift
let add = { (a: Int, b: Int) -> Int in
    return a + b
}
// can call add(3, 4)
```
- **[Use case](https://www.reddit.com/r/swift/comments/or7cz9/eli5_when_would_you_use_closures_instead_of/):** optional variable on child object 
	- Passing code blocks, callbacks, SwiftUI views
- **IMPORTANT:** 
	- Can capture variables from surrounding scope (i.e. if defined inside a function, it can remember variables inside that function)

**Trailing Closure:** where a closure is passed as final parameter outside parentheses
```swift
func doSomething(action: () -> Void) {
    action()
}

// Normal call
doSomething(action: {
    print("Hello from closure")
})

// Trailing closure syntax
doSomething {
    print("Hello from trailing closure")
}
```

**ALL FUNCTIONS** → first-class citizens (can be treated like any other type)

# References
https://www.geeksforgeeks.org/closures-in-swift/ 
