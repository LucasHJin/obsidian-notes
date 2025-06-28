2024-07-28 21:18

Status:
#in-progress

Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# Backend - web development explained

**==TO KNOW BEFOREHAND:==**
- [[REST explained |REST, RESTful APIs, RESTful principles]]
- [[HTTP explained |HTTP Requests, CRUD]]
- **Requests are made with HTTP, REST guides how resources are interacted with during these requests**

**What does backend do:**
- Code that runs on the server
- Receiving and processing requests from clients
- Storing data in [[Databases explained |databases]]

**Parts of backend:**
- **Server:** This is the computer that receives requests
- **App:** This is the application running on the server that listens for requests, retrieves information from the database, and sends a response
- **Databases:** Databases are used to organize and persist data

**Clients:**
- Anything that sends requests to the back end
	- I.e. browsers making requests for HTML and JS code to be executed

**Server:**
- A computer that listens to incoming requests

**Core functions of the app:**
- Logic to respond to requests based off of **[[HTTP explained |HTTP]] verb** and **Uniform Resource Identifier (URI)**
	- URI -> typically just URLs
	- The pair is called a **route**
	- Matching them based on request is called **routing**
- **Middleware:** any code that executes between the server receiving a request and sending a response
	- Basically handler functions that customize the request
		- I.e. change request object, query the database, etc.
	- Continue down the line (don't send back response) -> eventually will end and send response
	- A route can have 0+

**[[APIs explained |API]]:** 
- A collection of clearly defined methods of communication between different software components
- **Web API:** the interface created by the back-end
	- Collection of endpoints (of requests) and available resources from that
		- Defined by requests it can handle, routes and types of responses
	- Can provide data for multiple front ends

==**IMPORTANT:**==
- The server typically cannot initiate responses without requests!
- Every request needs a response (even 404 status)
	- Otherwise your client will be left _hanging_ (indefinitely waiting)
- The server should not send more than one response per request

**Backend languages/databases and [[Frameworks explained|frameworks]]:**
- Python and [[Django explained |Django]]
- [[Firebase]]
- [[Node explained]] 
	- [[Express explained]] 

# References
https://www.codecademy.com/article/back-end-architecture
