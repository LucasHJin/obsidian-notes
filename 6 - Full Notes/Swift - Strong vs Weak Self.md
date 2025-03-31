2024-11-01 08:13

Status:


Tags:
[[cs]]
[[ios]]


___________________________________________________________________________
# Swift - Strong vs Weak Self

![[Screenshot 2024-11-01 at 10.09.23 PM.png]]

**Strong vs Weak:** How memory is managed for objects
- Managed by the system based on if its strong or weak
- **Strong references:** Prevents the object that is being referenced from being deleted in memory
	- *Problem*: If a child and parent both strongly reference each other -> system leaks memory (is unable to clean up memory) because they each point to each other
		- ==Always want to avoid **memory leaks**==
			- Will often reference self in **weak** fashion:
```swift
handler: { [weak self] _ in
	self?.doSomething()
}
```
- Basically, anytime after {} where you need to pass in self to call a function, use `[weak self]` 
- Additionally, you can unwrap immediately inside of the function instead of optional:
```swift
guard let strongSelf = self else {
	return
}
```

- **Weak references:** Fixes problem of strong references
	- Parent retains strong reference but child has weak reference (if parent is cleaned up, so is child) but (if child is cleaned up, nothing happens to parent)
- Weak vs Strong will just notate its references to other objects
	- Automatic reference counting (counts how many references pointed toward an object)
		- If strong -> increments a count in memory if any object is strongly retained





# References

