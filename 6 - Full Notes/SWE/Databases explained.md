2024-07-28 22:57

Status:
#in-progress

Tags:
[[cs]]
[[webdev]]

___________________________________________________________________________
# Databases explained

**What?**
- An organized collection of structured information, or data
- **Examples:**
	- MongoDB, MySQL, etc.

**Why?**
- Provide an interface to save data in a persistent way to memory
	- Reduces load on main server
	- Allows safe storage of data
- Very common on any dynamic sites
- [[HTTP explained |Requests]] may require database queries
	- I.e. getting client information from a database like a previous purchase
	- I.e. putting client information onto a database like user information

**Types:**
- **Relational Databases (SQL databases):**
	- **Structure:**
		- Organized in tables (relations) with rows and columns
		- Each table has a defined **schema** specifying columns and datatypes
			- **Column:** Attributes/fields
			- **Row:** Records/entries into these fields + primary key
		- Relationships between tables are made with keys
	- **Keys explained:**
		- **Key:** a unique identifier which can be assigned to a row of data contained within a table
			- Is called primary key when in original table, foreign key when linked in another table
	- **Rules:**
		- Each foreign key must have a primary key
		- When a record in the primary table is deleted, all related records referencing the primary key must also be deleted
		- If the primary key is changed, all corresponding records in other tables using the primary key as a foreign key must also be modified
	- **Relationship types:**
		- **One-to-one:** A record in one table is related to one record in another table.
		- **One-to-many:** A record in one table is related to many records in another table.
		- **Many-to-many:** Multiple records in one table are related to multiple records in another table.
	- **Benefits:**
		- Data management consistency
		- Good security
		- Ease of backup and recovery
	- ==**Queried using [[SQL explained |SQL]]**==
	- **Example:**
		- Customer ID is a primary key in customer database, for the order database it becomes the foreign key
	- **Software:**
		- SQL Server Express, PostgreSQL, SQLite, MySQL and MariaDB
	
- **Non-Relational Databases (NoSQL databases):**
	- Uses a storage model optimized for specific requirements of the type of data being stored (no keys, tables, etc.)
		- Use various query languages or APIs to query them (no one specific)
	- **Document data store:**
		- String fields and object data are stored in documents (JSON documents)
		- Field within the document are exposed
	- **Columnar data store:**
		- Data is stored in columns (Similar to relational databases)
			- But, it has a denormalized approach to structuring sparse data
	- **Key value store:**
		- Collection of key and value pairs within an object
	- **Document store:**
		- Data in documents in collections -> retrieved through signal
			- I.e. firebase
			- [[Firebase - Firestore]] 
	- **Graph Databases:**
		- Efficiently stores relations between entities
			- I.e. good for purchases where items are linked
	- **Software:**
		- MongoDB, Apache Cassandra, Redis, Couchbase and Apache HBase


==**Database query in HTTP Request Example:==**
```
GET /users?name=John%20Doe HTTP/1.1
Host: example.com
Accept: application/json
```
>The server then processes the request to search for John Doe in database (I.e. SQL query)
```
SELECT * FROM users WHERE name = 'John Doe';
```
>The server executes the request, retrieves data and sends JSON response
```
[
  {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com"
  },
  {
    "id": 2,
    "name": "John Doe",
    "email": "john.doe2@example.com"
  }
]
```



# References
https://www.codecademy.com/article/back-end-architecture
https://www.pluralsight.com/blog/software-development/relational-vs-non-relational-databases

