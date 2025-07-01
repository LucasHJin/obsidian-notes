2025-06-03 22:48

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - APIs

Touched on in [[Backend - web development explained]] and [[APIs explained]] 

**What is it?** 
- A server that is created for serving data for external use (i.e. get data from database and feed it frontend)
	- Often → building a [[Backend - web development explained|backed]] is just building an API (i.e. [[REST explained|REST API]]) 
	- The endpoints (`/productions, /users, etc.`) are all API routes

**How to fetch data from APIs:** 
- Use `fetch` → native function for making [[HTTP explained|HTTPS]] requests
	- Returns a Promise
	- Requires manual parsing of JSON (`res.json()`)
```js
// URL (required), options (optional)
fetch('https://url.com/some/url')
  .then(function(response) {
    // Successful response :)
  })
  .catch(function(err) {
    // Error :(
  });
```
- Fetch part can get more complicated if it’s not a simple `GET`":
```js
const response = await fetch("Backend link", { 
    method: "POST",
    headers: {
        "Content-Type": "application/json" 
    },
    body: JSON.stringify({ data, passed, to, backend }),
    credentials: 'include'
});
```
- Or libraries like `axios` 
	- Also returns a Promise but has automatic JSON parsing

**Handling `.fetch`** 
- **OPTION 1**
	- `.then` → promise chaining
		- Check `res.ok` inside `.then` and need `.catch` for error handling
- ==**OPTION 2** ==
	- `async/await` → more like synchronous ([[Javascript - Async + Await|check this out]])
		- For more complicated logic or useEffect + more readable
```js
try {
  const res = await fetch('/api/data');
  const data = await res.json();

  if (res.ok) {
    console.log(data);
  } else {
    console.error('Error from server:', data.error);
  }
} catch (err) {
  console.error('Network error:', err);
}
```


**[[CORS explained|CORS]] (Cross Origin Resource Sharing):** enables you to avoid the problem of browsers implementing restrictions on HTTP requests to outside sources
- **Solutions:**
	- `{mode: 'cors'}` within the fetch
	- On backend → install CORS
```js
const cors = require("cors");
const app = express();
app.use(cors()); // allow all origins
```


# References

