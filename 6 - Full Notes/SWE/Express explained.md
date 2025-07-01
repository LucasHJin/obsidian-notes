2025-06-02 09:13

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Express explained

Often styled with [[MVC explained|Model - View - Controller]] design pattern 

[[Frameworks explained|Framework]] built on top of [[Node explained|Node.js]] 
- [[Express - Routes]] 
- [[Express - Controllers]] 
- [[Express - Views]] 
- [[Express - Auth]] 
	- [[Cookies explained]] 
- [[ORMs explained]] 
	- [[Prisma ORM explained]] 

**What do you need to connect:** 
- **Pool:** a manager that keeps a few database connections open so you don’t have to reconnect every time you run a query
- An express app → `const app = express();` 
- JSON parsing [[Express - Controllers|middleware]] → `app.use(express.json());`
- Database query functions → [[Express - Repository Pattern]] 
- Create routes and connect to DB functions ^^
- Start server
- Environment variables
```js
import dotenv from 'dotenv';
dotenv.config();
```


Example:
```js
const express = require("express"); // Import express
const app = express(); // Initialize app variable

app.get("/", (req, res) => res.send("Hello, world!"));

const PORT = 3000; // Backend port that needs to be accessed
app.listen(PORT, () => {
  console.log(`My first Express app - listening on port ${PORT}!`);
});
```
- `req` → request object (what is passed to backend)
- `res` → response object (what is sent back to frontend)
- Callback function → the arrow function


# References

