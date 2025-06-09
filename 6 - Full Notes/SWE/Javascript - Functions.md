2025-06-02 09:46

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# Javascript - Functions

***NOTE:*** When writing methods inside a class → don’t write `function`
- Just write it directly

**Functions:** a reusable block of code that performs a specific task or operation
- **Parameter:** items listed in the parentheses of the function
	- **Default parameters** → add a value with equal for optional parameter
- **Arguments:** the actual values that are passed into the function

**Types of functions:**
- **Default function:** just use `function name() {`
	- Hoisted → can call in global scope and before definition (rest is all unhoisted)
- **Anonymous function:** function without a name (use `(function () {`)
	- Used when a function expects to receive another function as a parameter → function parameter is passed as an anonymous
	- ![[Screenshot 2025-06-02 at 10.22.55 AM.png|500]] 
- **Arrow function:** alternative to writing an anonymous function
	- `(event) =>` instead of `function (event)`
		- If only 1 return statement → can also omit braces and return keyword
		- I.e. `.map(i => i + 2)` 
		- Preserves `this.` from surrounding context (i.e if in an object defining a person, can do `this.name`)
		- Good for callbacks + one liners
- **Function expression:** allows you to assign a value to a variable
	- ![[Screenshot 2025-06-02 at 10.28.07 AM.png|500]] 
- **[[Javascript - Async + Await|Async function]]:** good for async operations like HTTP requests or I/O
	- `async function`…
	- Returns a **promise:** built-in object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value
		- I.e. a future value that is to be given (**pending, fulfilled, rejected**)
	- **await:** stops the function until the promise is fulfilled (i.e. a request to the backend)
	- **For backend requests:**
		- Most of the time: `const fetchUser = async () => {`
			- Use async arrow function because it works same as default and fits well with event handlers and React


**Function scope:** the variables it can access are limited to that function (inside global scope)
- Ensures no problems with redeclaration across different functions for example

**Callbacks:** a function passed as an argument to another function, which is then executed at a later time
- I.e. if it’s passed as `c`, you can call it with `c()`
- Useful for:
	- Code running after an async operation
	- Want function customizability by letting caller pass in behavior


# References
https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Functions#anonymous_functions_and_arrow_functions 
https://javascript.info/function-expressions
https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Return_values
