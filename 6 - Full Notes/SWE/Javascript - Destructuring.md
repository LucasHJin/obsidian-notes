2025-06-03 15:23

Status:


Tags:
[[cs]] 
[[webdev]] 
[[mobile dev]] 

___________________________________________________________________________
# Javascript - Destructuring

A syntax that unpacks values from arrays or properties from objects into distinct variables
- Use either `[]` for lists and `{}` for objects
- Basically a concise way to extract individual pieces of data from objects 

I.e. 
```js
const person = {
  name: "Lucas",
  age: 18
};

const { name, age } = person;
```

**Use case:** 
- Extracting data (above ^^)
- Function parameters → destructure object passed as parameter into the individual values (same logic as react props)
	- Allows you to avoid repetitive `obj.prop` references
- Can also do smth similar with API responses/JSON data (i.e. get the individual id or title instead of doing like data.title)

**GETS PROPERTIES FROM WITHIN A CLASS/OBJECT** 
- I.e. if `contentEl` is a property of `this` → `this.contentEl` 
	- You can do: `const { contentEl } = this` 

# References

