2025-06-03 22:36

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - Asynchronous Code

A method for [[Javascript - Functions|functions]] to happen in the background while the rest of the code executes (**asynchronous**) → instead of pausing it and making all the code wait until it finishes

**Callback:** a function passed into another function as an argument (invoked to complete some action)
- I.e. adding to `addEventListener` → the function inside
- ==**Caution:**== Can lead to [callback hell](http://callbackhell.com/) 
	- You can have many callbacks and order jumps around, making your code slower and more confusing

**Promise:** an object that might produce a value at some point in the future (promise that the value will be returned)
- I.e. fetching data isn’t always instant so if you try to instantly access it → problem occurs
- Can create a new promise with `new Promise(resolve, reject) {}` or just `Promise.resolve` 
	- Resolve → function to call if successful 
	- Reject → function to call if fail
- **`.then` method**
	- Can react to the promise (do something with the return from the promise if **resolved**)
		- Can chain `.then` for multiple things to do
- **`.catch` method**
	- For if the promise returns a **rejection** 
		- Frequently → catch is for error
- **`.final` method** 
	- Callback that is called regardless of success/failure
- **`Promise.all`** → waits until all async operations are completed and then makes one callback for all of them
	- Opposite of `Promise.race` → first one to finish gets processed


# References
https://davidwalsh.name/promises
