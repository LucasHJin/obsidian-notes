2024-11-01 08:13

Status:


Tags:
[[cs]]
[[ios]]


___________________________________________________________________________
# Swift - Concurrency and Threading

**Concurrency:** Ability to do multiple tasks at the same time
- **Task:** units of work to be run
	- Can be made with `Task { ... }` 
	- Can be made with **async function** 
- Tasks are executed on **threads** 
	- **Threads:** small set of instructions that can be executed independently from the main program
		- **Main thread:** thread we want to keep fast (UI Thread)
		- **Background threads:** background tasks (time intensive tasks)
	- **Grand central dispatch + NSOperation Queues:** API built by Apple to handle heavy lifting of threads
		- *For developers:* Just work with queues of tasks
		- **Queue:** FIFO
			- **Serial queue:** Tasks don't start until previous is completely finished
				- Predictable execution order
				- Prevents race conditions
				- ==Use when tasks depend on others== 
					- I.e. 
			- **Concurrent queue:** Tasks start in correct order but speed and finishing is unknown 
				- Faster
				- Unpredictable order
				- ==Use when you don't care about order and you don't have any tasks dependent on others==
					- I.e. saving user preferences
		- Every app gets:
			- 1 main queue
			- 4 concurrent queues (also called **global queue**)
				- All tasks are automatically assigned to this queue if not manually assigned to main


```swift
DispatchQueue.main.async {
	self.tableView.reloadData() //example of reloading UI with data
}
```
- Switch to main queue

Can also move to background queue (not often though): 
```swift
DispatchQueue.global(qos: .background).async { //qos = quality of service
	//Code to run in background queue
}
```
- **QOS:** defines the priority and resource allocation for tasks running on dispatch queues (importance of task + how resources are allocated)
	- .userInteracted
	- .userInitiated
	- .default
	- .utility
	- .background

# References
https://www.youtube.com/watch?v=iTcq6L-PaDQ 
