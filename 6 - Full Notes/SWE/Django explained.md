2024-07-29 09:48

Status:
#not-started 

Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# Django explained

**What?**
- Is a high level Python [[Frameworks explained|framework]]
	- Follows a ==batteries-included== philosophy
	- This means that it comes with a comprehensive set of built-in features and tools
		- No need for third-party plugins or additional components to perform common tasks
		- I.e. Authentication, Admin Interface, Object-Relational Mapping, Form Handling, Routing, Security
		- **ORM:** Allows to handle [[Databases explained|database]] queries with Python instead of [[SQL explained|SQL]]/NoSQL

**Advantages:**
- Ease of speed and scalability in creation
- Lots of community support and documentation
- Is very secure
- Is versatile (i.e. can even perform machine learning)

**Disadvantages:**
- Not good for simpler projects (because is high-level -> may be slower)
- Can be slower for websites
- There is a lack of conventions
- It is very broad

**Structure:**
- Traditionally, a web application waits for HTTP requests from the web browser
	- Then, it processes the request before returning a response
	- (Often creates an HTML page for the browser to display by inserting the retrieved data into placeholders in an HTML template)
- Django groups the code for each of these steps into **separate files**:
	- **Urls:** `urls.py`
		- Separate view function to handle each resource
		- **URL mapper** redirects the request to the specific view based on request URL
			- Can also match particular patterns of strings or digits that appear in a URL and pass these to a view function as data
	- **Views:** `views.py`
		- Request handler functions -> takes request, gives response
		- Access the data to satisfy the request with **models**
			- Format the response with **templates**
	- **Models:** `models.py`
		- Python objects that define the structure of an application's data
			- Provide mechanisms to manage and query info in the database
			- (add, modify, delete, read)
	- **Templates:** `/templates/index.html`
		- A text file defining the structure or layout of any file (i.e. an HTML page)
			- Has placeholders used to represent actual content
		- Can be populated with information from the **model** by the **view**



# References
https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction
==**Tutorial:**== https://simpleisbetterthancomplex.com/series/beginners-guide/1.11/