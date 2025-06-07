2025-06-04 21:39

Status:


Tags:
[[cs]] 
[[ios]] 
[[mobile dev]]


___________________________________________________________________________
# Swift - Basic Syntax

**Variables:** 
- `var` → variables that can change
- `let` → constants that can’t change
	- Type safe (infers the type) → can also explicitly declare (type annotation)
	- i.e. `let temp: Double = 1.1`

**Strings:** 
- Use double quotes (or triple quotes for multiline)
- Can use interpolation to insert variables → `\(variable)` 

**Optionals:** symbols that mean a variable might contain a value, or might be nil
```swift
var nickname: String? = nil
nickname = "LJ"
```
- Prevents errors from using an uninitialized variable
- **Working with optionals:** 
	- **Optional binding** → **`if let`** 
		- Can set another variable to the optional (unwraps it and gets value if it exists)
			- If true → run code inside
	- **`Guard let`** → for early returns in functions
		- Code inside guard only runs when it’s false
		- Assign variable to the optional and if no value, run inside code (guarding)
	- **Forced unwrap** → just use `!` after the variable
		- DANGER OF CRASH
	- **Default option** → use double ? to set default
		- `let displayName = username ?? "Guest"` 

**Basic types:** 
- Int, Double, Float, Bool, String, Character
- Array, Dictionary, Set, Tuple, Optional

# References
https://www.programiz.com/swift-programming/guard-statement
