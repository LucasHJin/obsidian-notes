2025-06-02 20:39

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - Loops and Arrays

**Loops:** subprograms that run a set of instructions multiple times
- **For-of loop:** `for (const X of Y)` 
	- (iterating through a container of things)
- **For loop:** `for (initializer; condition; final-expression)` 
	- Like in c++ where you set a counter and increment it until a certain point
- **While loop:** `while (condition)`
	- Initializer is defined outside the loop, incrementer (FE) inside at the end
- **Do while loop:** `do { } while (condition)` 
	- Code is always executed at least once (condition is after the code)

**Break and continue** → immediately exists loop vs goes to the next iteration of the loop

**Arrays:** ordered collections of items (strings, numbers, or other things)
- Still declared with const or let just like variables
- Can have **DIFFERENT** types within the same array
- **Creation:** 
	- Use `[]` or `new Array()` 
	- First is better because second can create desired length but no actual items
	- Most typical way to create array of length X (use second):
		- `Array(x).fill(0);` 
		- `Array.from({ length: x }, (_, i) => i);` (from makes array from array-like object)
- ALWAYS use strict equality to compare arrays 
- **Methods:**
	- **.push, .pop, .shift, .unshift** → add and remove items from start and end
	- **.splice** → Deletes X elements starting from index and replaces with the elements
		- Can get the array of removed elements by assigning to a variable
	- **.slice** → Returns a new array from start index up to but not including end index
	- **.concat** → adds together two lists (not array-like objects)
	- **.forEach** → run a function for each value in array (no returned manipulated array)
		- `function(item, index, array)` 
	- **.map** → calls a function for each value in array (returns the new array)
	- **.filter** → returns array of all elements that satisfy the condition
		- **.find** → only returns first instance
	- **.reduce** → returns a single value based on iterating through the array
		- ![[Screenshot 2025-06-02 at 9.55.24 PM.png|550]]
		- - `accumulator` – is the result of the previous function call, equals `initial` the first time (if `initial` is provided).
		- `item` – is the current array item.
		- `index` – is its position.
		- `array` – is the array.
	- **.fill** → fills array with a value
	- **Spread operator:** `...iterable` 
		- spreads out elements of an array into individual elements (can put it in another array to make a new one)
		- I.e. `const arr = [1, 2, 3]; const copy = [...arr];`
	


# References

