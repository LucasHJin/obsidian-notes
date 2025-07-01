2025-06-28 21:55

Status:


Tags:



___________________________________________________________________________
# PostgresSQL explained


Starting:
```js
const { Pool } = require("pg"); // npm install pg

// Again, this should be read from an environment variable
module.exports = new Pool({
  connectionString: "postgresql://<role_name>:<role_password>@localhost:5432/top_users"
});
```
- Pool is better than client for multiple ppl

**Query parameterization:** Can pass user input as an array (second argument)
- Use `$1` to access 



# References

