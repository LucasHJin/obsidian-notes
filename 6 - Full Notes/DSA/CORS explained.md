2025-06-29 20:51

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# CORS explained

[**Same origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy):** only requests from the same origin (IP / URL) can access this API
- For security
- **Cross Origin Resource Sharing (CORS)** → allows us to avoid this problem
	- Can set up in [[Express explained|Express]] with a middleware
I.e.
```js
let cors = require('cors')
app.use(cors())
```

**Preflight:** the browser asking for permission before sending certain types of requests to a server on a different origin
- If simple request → allowed immediately
- Else → browser sends a small request using the OPTIONS method (ask if it is allowed to send a request with the given headers and methods)

Typical configuration:
```js
{
  "origin": "*",
  "methods": "GET,HEAD,PUT,PATCH,POST,DELETE",
  "preflightContinue": false,
  "optionsSuccessStatus": 204
}
```

*In development:* 
- Allow access from any origin (`*`)

*In production:* 
- Block access from anywhere that is not your website
	- [See here](https://expressjs.com/en/resources/middleware/cors.html#enabling-cors-pre-flight) 




# References

