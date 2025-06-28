2024-07-29 09:28

Status:
#not-started

Tags:
[[cs]]
[[webdev]]

___________________________________________________________________________
# SQL explained

**SQL (Structured Query Language):** Language to interact with a relational database 
- *Declarative language* → describes what to do but not how to
- ALL TABLES HAVE AN ID → can be queried by SQL
	- Allows for relationships between databases ([[Databases explained|primary + foreign keys]]) 
		- Have one table point to another table’s id (i.e. table_id) → foreign

*Note:* Use semicolons and single quotes.

**Commands:** 
- *Setting up:* 
	- `CREATE DATABASE`
	- `CREATE TABLE` 
	- Setup information is stored in a **schema** file (updated with changes)
		- I.e. there is a table of users with id and another table of XX
	- `CREATE INDEX` → pre-organize column to make data easier to query
		- `CREATE INDEX idx_users_username ON users(username);` → improve the search-ability of the username column in the users table
	- `UNIQUE` → all different values
- *Interacting with data:* 
	- Mostly [[HTTP explained|CRUD]] actions
		- **Syntax** → the action (“statement”), the table it should run on, and the conditions (“clauses”)
		- Can use comparison operators and logical operators (AND, OR, ≤, etc.)
			- Note → only single equal for equality
	- `INSERT INTO ... VALUES` → create (generally include column headers)
	- `DELETE ... WHERE` → delete with conditions
	- `UPDATE ... SET ... WHERE` → update a table with new data based on a query
	- `SELECT ... FROM ... WHERE` → reading values
		- Generally include table names
		- `SELECT DISTINCT` → no duplicates
- *Combining tables:* (use typically alongside `SELECT`)
	- `ON` → dictates which columns to use to combine
	- `JOIN` → performs the combining (`OUTER` is optional)
		- `INNER JOIN` (same as `JOIN`) → Keeps only the rows from both tables where they match up
			- Like intersection
		- `LEFT OUTER JOIN` → Keeps all rows from left table and adds right table where applicable or `NULL` 
		- `RIGHT OUTER JOIN` → Same as `LEFT JOIN` but with right priority
		- `FULL OUTER JOIN` → Keeps all rows from all tables, mismatched cells are set to `NULL` 
			- Like union
	- Example: `SELECT * FROM users JOIN posts ON users.id = posts.user_id;`
		- Joins `users` and `posts` 
		- Matches rows where `user.id = posts.user_id` 
		- Returns all columns from both tables for each matching row
- *Aggregating data:* 
	- `SUM`, `MIN`, `MAX`, `COUNT` 
	- `AS` → rename columns / aggregate functions to be called by alias later on
		- `SELECT MAX(users.age) AS highest_age FROM users` → returns column called `highest_age` with max age
	- `HAVING` → where but for aggregates
	- `GROUP BY` → group rows that have the same value in one or more columns (to be able to perform aggregate functions on them)
	- 




# References

