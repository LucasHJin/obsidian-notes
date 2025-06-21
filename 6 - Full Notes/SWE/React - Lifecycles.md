2025-06-19 17:25

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - Lifecycles

**Components:** 
- mounts when added to screen
- updates (rerenders) when receiving new props/states
- unmounts when removed


**Effect lifestyle** is different → involves synchronizing current props and state with outside system
- Body → how to start synchronizing
- Cleanup function → how to stop synchronizing
- Dependencies → when to synchronize
- **Note:** focus on a single start/stop cycle at a time
	- Just know in what cases it needs to start/stop
- I.e. for switching rooms (start when a new room, stop when exiting current room)

**Note:** Each Effect in your code should represent a separate and independent synchronization process
- Because the entire code runs each time ANY of the dependencies are called

**Reactive variables:**  variables that automatically update the UI or trigger effects when their value changes
- Must be included in dependencies



# References
https://react.dev/learn/lifecycle-of-reactive-effects
