2024-11-06 20:09

Status:


Tags:
[[cs]] 
[[webdev]]


___________________________________________________________________________
# Firebase - Firestore

Is a [[Databases explained|NoSql]] cloud database
- Uses **collections** + **databases**:
	- **Collection**: Container for documents
		- (Like a table in a relational database)
		- No fixed schema -> can take on any structure of data
	- **Document:** a unit of data with key value pairs
		- Each document has unique ID
			- Can have various fields (i.e. boolean, string, int, etc.)
		- Not all documents need to contain the same fields

Example:
```javascript
/users (Collection)
  /userId (Document)
    - name: "John Doe" (Field)
    - email: "john@example.com" (Field)
    - createdAt: Timestamp (Field)
  /userId2 (Document)
    - name: "Jane Doe" (Field)
    - email: "jane@example.com" (Field)
    - createdAt: Timestamp (Field)
```

**Key features:** 
- Real-time updates
- Offline support
- Security rules -> for who can read/write to the database

**Querying:** 
- Simple queries (filter by field)
- Compound queries (filter by multiple fields)
- Sorting (order data based on fields)
- Range queries (use operators like <=, >, etc.)


**How to write (JS):** 
Use `.set()` after the list of all the collections and documents
```javascript
const db = firebase.firestore();

// Adding a document to a collection
db.collection("users").doc("userId123").set({
  name: "John Doe",
  email: "john.doe@example.com",
  age: 30
})
```

**How to read (JS):** 
Use `.get()` with `.where()` for conditions
```javascript
db.collection("users")
  .where("age", ">", 25)
  .get()
  .then((querySnapshot) => {
    querySnapshot.forEach((doc) => {
      console.log(doc.id, " => ", doc.data());
    });
  })
  .catch((error) => {
    console.log("Error getting documents: ", error);
  });
```

# References

