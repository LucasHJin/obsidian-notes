2025-06-03 23:06

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - Async + Await

**What are they?** 
- Keywords that make it easier to read like synchronous code (cleaner)

`async` **keyword**:
- Tells the processor that you are creating an asynchronous function (can use it for any function)
	- Necessary for `await` 
- Returning in this function = resolving a promise (automatic promise)
	- Throwing error = rejecting a promise

`await` **keyword**:
- tells JavaScript to wait for an asynchronous action to finish before continuing the function (pause the flow of logic within the function until promise is resolved)
	- Replaces `.then()` → assigns value to variable using `await` 

**Error handling:** 
- `try/catch` blocks
	- Can be used for async and sync code
	- Put the logic in try and any errors can be processed in the catch bock
- append `.catch()` to the end of the function
	- Because technically it’s just returning a promise

Can use `Promise.all` for it:
- can put `await` in front of a `Promise.all` wrapping multiple promises (i.e. fetching multiple info)

# References
https://javascript.info/async-await
