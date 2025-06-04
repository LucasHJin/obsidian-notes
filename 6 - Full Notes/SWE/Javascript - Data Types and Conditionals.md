2025-06-02 09:14

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# Javascript - Data Types and Conditionals

**Data type:** the type of thing a variable belongs to
- **Dynamically typed** → variables can change types at any time
- **Number**: includes all normal numbers, NaN, Infinity
	- Math is safe → code will never have an error and crash
- **BigInt**: bigger version of a number
- **String:** letters, words and phrases
	- Single and double quotes are the exact same
		- Can use one and then the other if you want to include quotations
		- OR → escape the character using a \ before the char
	- Backticks → allow for embedding code (`${}$`)
	- Can manipulate with [methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) 
- **Boolean:** true/false (logical)
- **null:** just a special value that represents nothingness (not referencing a non-existent object)
	- This means it can be queried, manipulated, etc.
- **undefined:** value not yet assigned
- **Object**: *ONLY non-primitive data type* → for more complex data structures

**Typeof**: allows us to see which type is stored in a variable (including function)
- Exceptions → null returns Object

**Conditionals:** code that expresses a condition and runs different programs based on the returned boolean
- **If, else, else if:** readable by humans
	- Allows for giving a bunch of choices
- **Switch:** less cumbersome syntax → take a single expression as input and then finds choice that matches the value
	- Need a default case for if all else fails
```js
switch (expression) {
	case choice1:
		break;
	default:
		break;
}
```

**Ternary operator:** single line operator for boolean expressions
- `condition ? run this code : run this code instead` 

**Regex:** regular expressions → find character combinations/patterns in strings
- For direct match → just use simple characters, i.e. `abc`
- For indirect match → use special characters
	- I.e. star means 0+ of the previous character
	- Can still use \ to escape characters

# References
https://javascript.info/types 
[String methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) 
[Conditionals](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Conditionals) 
[Regex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions) 