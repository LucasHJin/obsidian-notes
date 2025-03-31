2024-07-28 22:23

Status:
#finished

Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# REST explained

**Representational State Transfer**
- Architectural style for providing standards between computer systems on the web -> makes it easier for systems to communicate (**Method of designing [[APIs explained |APIs]]**)
- **Explained in simple terms:** 
	- Everything is a resource (users, posts, products, etc.)
		- All resources have a specific url/link
	- ==REST uses [[HTTP explained |HTTP]] methods==
		- **GET** to retrieve data,
		- **POST** to create new data,
		- **PUT** to update existing data,
		- **DELETE** to remove data.
	- **Stateless**: Clients and server are able to work without any information about the other
		- Each request from a client to a server must contain all the needed information
		- The server doesn’t remember any state from previous requests
		- Provides reliability, quick performance, and scalability
	- **Headers and Accept Parameters:**
		- **Headers:** key-value pairs sent in the HTTP request or response
			- Provide metadata about the request or response
			- I.e. content type (what it is providing), accept (what the response accepts), authorization, etc.
		- **Accept Parameters**: part of the HTTP request header
			- Tells the server what types of responses the client can process (media types)
			- ==Specifically for the header that is the Accept field==
			- In the **Accept field**
				- text — text/html, text/plain, text/css
				- image — image/png, image/jpeg, image/gif
				- audio — audio/wav, audio/mpeg
				- video — video/mp4, video/ogg
				- application — application/json, application/pdf, application/xml, application/octet-stream
	- **Paths:**
		- Path to a resource that the operation should be performed on
		- Should be descriptive and **first part** should be plural form of the resource
			- I.e. "fashionboutique.com/customers/223/orders/12"
				- order id = 12
				- customer id = 223
	- **Specify the HTTP version:**
		- Generally **HTTP/1.1** works for everything
		- **HTTP/2** and **HTTP/3** can be faster

- **Example scenario:**
	- **Client:** access resource in articles, id 23
		- GET /articles/23 HTTP/1.1
		- Accept: text/html, application/xhtml
	- **Server:** it worked with the content type
		- HTTP/1.1 200 (OK)
		- Content-Type: text/html
	- **CAN ALSO HAVE A BODY SOME TIMES IF POST**

**General format:**
```
HTTP METHOD | URL | HTTP PROTOCOL
Header-Name: Header-Value
...
Body
```

# References

https://www.codecademy.com/article/what-is-rest