2025-06-02 09:10

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Node explained

**Node.js:** an aysnchronous JavaScript runtime environment that allows you to run JavaScript outside of your web browser
- Installed using Node Version Manager (nvm)
- Managed with Node Package Manager (npm)
- Added functionality → read/write local files, create HTTP connections, listen to network requests
- **Asynchronous** → don’t need to worry about order or waiting for each function to finish
	- Can happen simultaneously
- Facilitated through [[Javascript - Asynchronous Code|callbacks]] 

Often used to build backend services ([[APIs explained|APIs]])
- Uses non blocking async code to handle many tasks at the same time
- Allows it to run on a server/own machine instead of through chrome

**JS Event Loop:** the queuing of things javascript needs to do
- **Call stack** → where JS runs functions
- **Web APIs** → handles things like setTimeout, fetch, etc.
- **Callback queue (task queue)** → where finished tasks from Web APIs wait to run
- **ORDER:**
	- JS runs code line by line and adds functions to the call stack
	- If something async → send to Web APIs to be handled (rest of the code continues to be processed)
	- When async task is done, callback goes into the queue
		- I.e. the callback → stuff inside the `setTimeout`
	- **Event loop** checks → if call stack is empty, run the callback queue



# References

