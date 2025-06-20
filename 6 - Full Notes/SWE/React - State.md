2025-06-07 12:22

Status:


Tags:
[[cs]] 
[[webdev]] 



___________________________________________________________________________
# React - State

**State:** a component’s memory
- Allows it to remember stuff about itself and change from HCI (human computer interactions)

**Explanation:** 
- When a component’s state/props change → destroyed and recreated
	- Rerenders based on latest value from useState
	- It rerenders the virtual DOM and compares to the actual DOM

*Note:* State is fully private and local to the variable declaring it
- Doesn’t impact other instances of state and can’t be modified by parent component

**Structuring state:** in general, if it can be calculated, don’t make it a state value (just calculate it each time you need it)
- State should never be mutated
	- I.e. for lists/objects, use spread operator + `set` instead of just manually editing it
	- (Provide a new, copied, object to tell [[React - useState|useState]] to rerender)
- **General rules:** 
	- Group related states
	- Avoid contradictions between states
	- Avoid redundancy 
	- Avoid duplicated states (i.e. copying a list)
	- Avoid deeply nesting states (i.e. 3D Lists)

**To note:**
- **State updates are async** → within a local scope, state stays the same in the current rendering of a component (i.e. changing the value doesn’t immediately make it a new value → need to wait for update)
	- [“state as a snapshot”](https://react.dev/learn/state-as-a-snapshot) 
	- *State update process* → function is called again, returns a new JSX snapshot of the component, updates screen to render that snapshot
- To update state multiple times based off of the last state → use **[[Javascript - Asynchronous Code|call back functions]]** 
	- I.e. 
```js
const handleIncreaseAge = () => {
  setPerson((prevPerson) => ({ ...prevPerson, age: prevPerson.age + 1 }));
  setPerson((prevPerson) => ({ ...prevPerson, age: prevPerson.age + 1 }));
};
```

**Sharing state between parents & childs** → single source of truth
- Have state all managed by one parent
	- Can pass info to children and vice versa (don’t duplicate state between child components)

**Controlled components:** 
- Can control HTML elements with your own state rather than its internal state (i.e. `input`) 
	- Set its value equal to `{value}` where value is a state

**Note:** within a single render’s event handlers (i.e. onClick) → state value is fixed
- Even if you wait on a timer or smth
- **Accessing future state update** → [State updater function](https://react.dev/learn/queueing-a-series-of-state-updates) 
	- Is just an arrow function (gets added onto queue → everything else replaces queue)
		- I.e. `e => !e` (use first letters of state names)


**Concepts:** 
- [[React - Hooks]] 
- [[React - useState]] 




# References

