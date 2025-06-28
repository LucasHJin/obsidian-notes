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

