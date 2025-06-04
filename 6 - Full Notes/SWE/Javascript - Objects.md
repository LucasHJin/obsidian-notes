2025-06-02 22:37

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - Objects

**Objects:** collections of key-value pairs
- Not a primitive data type (can store more than just 1 thing) → so it gives you a reference to the data instead of a copy
	- Can create with `{}` or `new Object()` 
	- Can get the values with either dot or square brackets (like an array)
	- Use `[X]` around X where it is the key to make it take the value of that variable
- **For-in loop:** `for (key in object)` 
	- Allows you to access all keys in an object

**Design pattern:** a reusable solution to a commonly occurring problem when designing a software application
- Can use objects to organize data
- **Object constructors:** regular function that by convention is named with an uppercase initial letter 
	- **Like a class in Python**
	- Declare it and then pass in attributes (`this.name = name`) 
		- Create an instance with `new Class` 
	- Same with functions (`this.sayName = function(){}`)
	- Can safeguard by guarenteeing you add `new`
		- ![[Screenshot 2025-06-02 at 11.17.51 PM.png|500]] 

**Prototype:** another object that the original object inherits from (inherits methods and attributes)
- All objects have a prototype
- Can define functions or attributes on the original prototype (i.e. `Player.prototype.sayHello`) 
- **Common practice:** 
	- ==Only define functions on the prototype and not in the constructor==
- **How to access an object’s prototype:** 
	- `Object.getPrototypeOf(X)` 
		- `.__proto__` is same but not recommended
		- `.[[Prototype]].` same with this (not recommended) 
- **Use:** 
	- Can define common functions and attributes to save memory
	- **Prototypal inheritance** → can inherit from prototypes
		- I.e. Chains from `player1` → `Player()` → `Object()` (base prototype for all)
- **Recommendation:** 
	- Use `Object.setPrototypeOf()` to change prototype and methods it inherits
	- ![[Screenshot 2025-06-03 at 10.54.00 AM.png|400]] 
	- Can create 2 separate objects but make one inherit from other
		- *Need to set prototype before creating any objects (instances)* 
	- **Never manually equate the two prototypes** → will all reference same thing and can change accidentally

`this` **keyword**:
- References the object of which the function is a property
	- I.e. if function A inside object B, using `this` in A references the object B
- **Global context:** 
	- References global object on Node.js / window object
	- 



# References
https://javascript.info/object 

https://www.digitalocean.com/community/tutorials/understanding-prototypes-and-inheritance-in-javascript

https://www.javascripttutorial.net/javascript-this/