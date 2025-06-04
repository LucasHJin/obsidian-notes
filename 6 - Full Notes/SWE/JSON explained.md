2025-06-03 22:15

Status:


Tags:
[[cs]] 
[[webdev]] 
[[mobile dev]] 


___________________________________________________________________________
# JSON explained

**JSON ([[Javascript Explained|JavaScript]] Object Notation):** standardized format for structuring data
- Very similar to syntax of javascript objects
	- Used for transferring data (i.e. APIs, servers, etc.)
- **Syntax restrictions:** 
	- Can only have serialized data types (i.e. no NaN or functions)
	- Strings + keys must have double quote
	- Objects/arrays can’t have trailing commas

I.e. 
```js
const resData = await res.json();
console.log(resData.property) // property passed from backend/api
```

**JSON Methods:** 
- `parse()` → Accepts a JSON as a parameter, and returns the corresponding JavaScript object
- `stringify()` → Accepts an object as a parameter, and returns the equivalent JSON

# References
[Check for JSON formatting errors](https://jsonformatter.curiousconcept.com/) 