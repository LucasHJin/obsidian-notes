2025-06-27 21:12

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Express - Controllers

**Middleware:** functions that operate between the incoming request and the final intended route handler (core feature of Express)
- Takes `req`, `res`, `next` (and sometimes `error`) 
- **Uses:** 
	- Modifying the request or response objects
	- Executing additional code (i.e. validation → chain with `.next()`)
	- Calling the next middleware function in the chain
	- Ending the request-response cycle
- **App level middleware:** bound to an instance of Express with `app.METHOD` 
	- Executes for every matching path
	- I.e. can be body parsers or serve static files (deliver files directly to browser)
- **Router level middleware:** bound to an instance of the Express router with `router.METHOD` 
	- Only runs when request matches and goes through router
- *NOTE* → the order in which middleware functions are placed matters!!!
	- A lot of the time → middleware is just 
Example:
```js
function myMiddleware(req, res, next) {
  // Perform some operations
  console.log("Middleware function called");

  // Modify the request object
  req.customProperty = "Hello from myMiddleware";

  // Call the next middleware/route handler
  next();
}

app.use(myMiddleware);
```
- Middleware after this can access the `req.customProperty` 
- [[Express - Important Middleware]]

*Note:* **ROUTES ARE NOT THE SAME AS MIDDLEWARE** 
- Both same syntax → `func(req, res, next)` ([source](https://medium.com/@viral_shah/express-middlewares-demystified-f0c2c37ea6a1)) 
- Route will process the information and send a response while middleware modifies the request or response in some way

**Controller:** functions that are also classified as a middleware but ==used by route handlers== 
- Act as a middleman between the server and the browser
- Key part of MVC ([[MVC explained|Model-View-Controller pattern]]) 
- Is used when a route matches HTTP verb and path
	- Based on middleware chain → route determines which controller should take over to fulfill the request (i.e. processing data, update model, make decisions)
	- Then it passes the processed data to the [[Express - Views|view]] 
		- Renders it into suitable format (i.e. JSON or HTML) 
**Example:** gets authorId from `req.params`, invokes database query, returns a response with status code and message
```js
// controllers/authorController.js
const db = require("../db");

async function getAuthorById(req, res) {
  const { authorId } = req.params;

  // getAuthorById is a utility/helper function that can be a part of a class 
  const author = await db.getAuthorById(Number(authorId));

  if (!author) {
    res.status(404).send("Author not found");
    return;
  }

  res.send(`Author Name: ${author.name}`);
};

module.exports = { getAuthorById };

// routes/authorRouter.js

const { Router } = require("express");
const { getAuthorById } = require('../controllers/authorController');

const authorRouter = Router();

// ... other route handlers
authorRouter.get("/:authorId", getAuthorById);
```
- **IMPORTANT**:
	- Generally → you want to be able to keep your route handlers as one-liners
	- Best practices → use an [[ORMs explained|ORM]] or use [[Express - Repository Pattern|Repository Pattern]]


**Handling responses:** 
- `res.send` → general purpose method for sending back a response
- `res.json` → sends back JSON data specifically
- `res.redirect` → allows for redirecting user to different URL
- `res.render` → render a view template + send resulting HTML as response
- `res.status` → sets status code (**doesn’t end request-response cycle**) 
- *Note* → only end the cycle, not the function
	- I.e. can still use 

**Handling errors:** 
- Use `try/catch` inside the controllers
- `next(error)` → automatically catches any thrown errors and passes control to a special **Error middleware handler** 
	- **Error middleware handler:** handles all errors in code (place at bottom) (NEED ALL 4 PARAMS)
```js
app.use((err, req, res, next) => {
  console.error(err);
  res.status(500).send(err);
});
```
- Create custom errors → extend the Error object to make a custom class

**Notes on `next`:** 
- `next()` → pass control to next middleware function
- `next(new Error())` → pass control to error middleware function
- `next('route')` → pass control to the next route handler with the same matching path (if there is one)
	- Does not work for `.use()` 
- `next('router')` → skip all middleware functions attached to the specific router instance and pass control back out of the router instance
	- Exit out of current router and go to parent (`app`) 


# References

