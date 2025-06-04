2025-06-03 11:22

Status:


Tags:
[[cs]] 
[[webdev]] 
[[mobile dev]] 


___________________________________________________________________________
# Javascript - ES6 Modules

**Module patterns:** ways of organizing code to keep it clean, reusable, and maintainable
- Only show and hide certain parts

**IIFE**: a JavaScript function that runs immediately after it is defined (**brackets around the function**) 
```js
(function() {
  // code inside the function
})();

(() => {
  // code inside the function
})();
```
- Creates a private scope (encapsulates the code inside of it)

**ES6 modules**: allows code to be split across multiple files with isolated scopes, so variables and functions are not globally scoped by default
- Helps with organization, encapsulation and reuse
- **Private scope by default → choose what you want to import/export** 
- **Types of import/export:** 
	- **Named:** 
		- Add `export` in front of function or `export {}` at the end
			- Can then import with `import {}` 
		- *Note:* This is not related to [[Javascript - Destructuring|destructuring]] 
	- **Default:** 
		- Add `export default` before the function/variable
			- Can only default export ONE thing
			- Has no name attached to it → import can name it whatever it wants
				- No curly braces when importing

# References
https://www.theodinproject.com/lessons/javascript-es6-modules
