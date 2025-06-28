2025-06-24 18:37

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# React - Reducing State

**Reducer:** pure functions that take a previous state and an action to return a new state
- Action → object with type property describing user action
	- Also has necessary properties to make new state
- **Don’t mutate state**

**Use cases:** when managing state gets more complex
- Separate state logic + easier testing 

`useReducer` → hook that allows using reducer function in components
- Takes reducer function + initial state as arguments
- Returns current state + `dispatch` function
	- `dispatch`: receives an action object as argument → passed to reducer function, returned value updates the state

```js
function reducer(state, action) {
  switch (action.type) {
    case "incremented_count": {
      return { count: state.count + 1 };
    }
    case "decremented_count": {
      return { count: state.count - 1 };
    }
    case "set_count": {
      return { count: action.value };
    }
    default: {
      throw new Error("unknown action: " + action.type);
    }
  }
}

const [state, dispatch] = useReducer(reducer, { count: 0 });

function handleClick() {
  dispatch({ type: "incremented_count" });
}
```

**How to switch from state to reducer:** 
1. **Move** from setting state to dispatching actions.
	1. Specify what user just did instead of what to do
2. **Write** a reducer function.
	1. Takes current state → updates with new state based on conditionals
		1. Typically use `switch` 
3. **Use** the reducer from your component.

# References
https://react.dev/learn/extracting-state-logic-into-a-reducer
