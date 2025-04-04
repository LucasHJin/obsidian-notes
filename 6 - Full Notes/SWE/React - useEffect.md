2024-09-27 09:55

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - useEffect

**UseEffect:** Tells React to do something when:
- A component re-renders (i.e. when state changes)
	- `useEffect(() => {})` (every re-render)
- A component is mounted (created and appended to the DOM) 
	- `useEffect(() => {}, [])` (only on mount)
- A variable's state is changed
	- `useEffect(() => {}, [value])` (only on mount + when value changes)
- ==Better name: useSideCode== 
	- Write the side code in a function + optional dependencies array
		- `useEffect(function, [dependencies])` 
- **Note:**
	- Strict mode makes it run twice (2x)

**Usecases:** 
- Event listeners
- DOM manipulation
- Subscriptions (realtime updates)
- Fetching data from an API
- Cleaning up when a component unmounts (removed from DOM) 

**Benefits:** 
- Keeps code more organized
	- Tell when exactly useEffect code runs

**Clean up functions:** 
```js
useEffect(() => {
	return () => {
		//Clean up code
	};
}, []);
```
- For cases where you need to do something before unmounting
	- I.e. removing event listener if used and then unmounted

**Example:** 
- Make title update each time
```js
useEffect(() => {
	document.title = `Count: ${count}`;
});
```
- Make title update once
```js
useEffect(() => {
	document.title = 'My computer program';
}, []);
```
- Make title update when count is updated -> makes it more efficient/precise
	- I.e. if there is another button, won't re-render however
```js
useEffect(() => {
	document.title = `Count: ${count}`;
}, [count]);
```
- Can put multiple state variables as dependencies
```js
useEffect(() => {
	document.title = `Count: ${count}`;
}, [count, color]);
```
- Make sure you only use one event listener instead of multiple
	- So that it doesn't create a new one each time the component re-renders
	- And cleanup
```js
useEffect(() => {
	window.addEventListener("resize", handleResize);

	return () => {
		window.removeEventListener("resize", handleResize);
	};
}, []);
```

# References

