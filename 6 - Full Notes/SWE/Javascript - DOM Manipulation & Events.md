2025-06-02 22:03

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - DOM Manipulation & Events
##### Note: not that useful for React because you aren’t manually changing DOM

**Document Object Model:** a tree-like representation of the contents of a webpage
- Has many nodes with relationships with each other 
	- I.e. divs are nodes and can have parent/child nodes, each on separate branch
- **Node:** a single point in the hierarchical structure that represents an HTML or XML document

**Selectors:** allow you to target specific nodes
- I.e. `div.display` (CSS)

**DOM methods:** allow you to use selectors to manipulate DOM
- **Query selectors:** 
	- `element.querySelector(selector)` → reference to first match
	- `element.querySelectorAll(selectors)` → list of reference to all matches
		- Can convert NodeList to Array with Array.from() or spread
- **Element creation:** 
	- `document.createElement(tagName, [options])` → can create a new element (i.e. div) 
		- Doesn’t place it on the page (just in memory to be manipulated)
- **Append elements:** 
	- `parentNode.appendChild(childNode)` → last child node
	- `parentNode.insertBefore(newNode, referenceNode)` → inserts as a child before reference node
- **Remove elements:** 
	- `parentNode.removeChild(child)` → removes child from parent Node + returns reference

**Events:** actions that occur on your webpage, i.e. mouse-clicks or key-presses
- **Method 1 - specify function attributes directly on HTML** 
	- I.e. within the button’s onClick
- **Method 2 - `on<EventType>`** 
	- I.e. Query the button and then access it’s onClick there
- **Method 3 - event listeners with DOM manipulation** 
	- I.e. Query the button and then .addEventListener

**e parameter** in callbacks:
```js
btn.addEventListener("click", function (e) {
  console.log(e);
});
```
- Object that references the event itself
	- Gives info like which mouse button or key was pressed, or information about the event’s target - the DOM node that was clicked
# References

