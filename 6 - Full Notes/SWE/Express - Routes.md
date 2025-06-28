2025-06-27 14:42

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Express - Routes

**Routes:** match a request’s [[HTTP explained|HTTP]] verb (e.g. GET or POST) and URL path to the appropriate set of middleware functions ([[Express - Controllers|controllers]]) 

**Anatomy of routes:**
```js
app.get("/", (req, res) => res.send("Hello, world!"));
```
- Choose the HTTP verb
	- Can use `app.all()` to match with all HTTP verbs
- Pass a route (path to match with frontend)
	- `{}` → makes path optional (i.e. `"/message{s}"`) 
	- **Splat** → match any number of characters `"/{*splat}"` 
		- Good for error handling
		- *NEEDS TO BE LAST* → order matters
- *Note:* Can also have `next` alongside `req` and `res`
	- Passes a callback to the next [[Express - Controllers|middleware]] function
- **Route parameters:** for dynamic routing (i.e. passing id's)
	- Use `:` followed by case-sensitive alphanumeric characters
	- `req.params` → automatically populated with the value passed in the parameter (the parameter name is the key)
I.e. 
```js
/**
 * GET /odin/messages/79687378 will have this log
 * { username: "odin", messageId: "79687378" }
 */
app.get("/:username/messages/:messageId", (req, res) => {
  console.log(req.params);
  res.end();
});
```
- **Query parameters:** optional part of URL that starts with `?` and is key-value pairs
	- I.e. `/odin/messages?sort=date&direction=ascending` 
	- `req.query` → automatically populated

**Organizing with routers:** You can create routers in individual files and make routes starting from each of those routers
- Then, import them in the original file with `require` 
```js
const express = require("express");
const app = express();
const authorRouter = require("./routes/authorRouter");
const bookRouter = require("./routes/bookRouter");
const indexRouter = require("./routes/indexRouter");

app.use("/authors", authorRouter);
app.use("/books", bookRouter);
app.use("/", indexRouter);

const PORT = 3000;
app.listen(PORT, () => {
  console.log(`My first Express app - listening on port ${PORT}!`);
});
```

[**POSTMAN**](https://www.postman.com/downloads/) → Allows you to check if routes are working with `GET` and `POST` requests out of browser

# References
https://expressjs.com/en/guide/routing.html
