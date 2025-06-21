2024-09-26 13:49

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# Javascript - onChange

**onChange:** event handler that is used to capture and respond to changes in input fields
- I.e. text inputs, checkboxes, and dropdowns
	- ==Access new value with:== `event.target.value` 
	- Need to pass `event` to new function
- Put it in the input field
	- I.e. `<input type="text" value={inputValue} onChange={handleChange} />` 

I.e. 
```js
function handleChange(event) {
  console.log(event.target.value); // Accessing the new value
}

<input type="text" onChange={handleChange} />
```


# References

