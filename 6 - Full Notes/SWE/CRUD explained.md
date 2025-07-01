2025-06-29 20:19

Status:


Tags:



___________________________________________________________________________
# CRUD explained

**CRUD:** 
- **Create - POST**
	- Used to create new resources
	- Typically have a request body -> user specifies attributes of resource
		- In JSON
	- I.e. adding a new product to a store
- **Read - GET**
	- Access either all resources/specific resources of a certain type
	- Typically no request body (not trying to change anything)
- **Update - PUT / PATCH**
	- PUT:
		- Replace **existing resource** with an updated version
		- Replaces the entire resource
			- Any left out attributes from the body are deleted, any new attributes are added
	- PATCH:
		- Also used to update an **existing resource**
			- Enables updating specific attributes without overwriting others
			- Makes it more efficient (don't have to fill in all attributes and fields each time)
		- I.e. only updating price, not name, color or currency
- **Delete - DELETE**
	- Request to permanently remove resource at the given URL
		- May require authorization mechanisms
	- I.e. for /products/123 -> will delete product with ID 123

# References

