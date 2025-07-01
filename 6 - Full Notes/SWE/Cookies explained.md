2025-06-29 12:24

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Cookies explained

**Cookies vs localStorage:** 
- *Cookies* → small key-value pairs stored by the browser (4KB)
	- Sent automatically with every HTTP request
	- *Pros/Uses:*
		- Useful for secure tokens (auth), server-rendered apps, managing sessions
	- *Cons:*
		- Small storage, requires careful setup
- *localStorage* → larger key-value stores (5-10MB) in browser
	- Need to manually send with HTTP requests
	- *Pros/Uses:* 
		- Can cache non-sensitive data + store UI state/preferences easily
	- *Cons:* 
		- NOT SECURE → vulnerable to XSS (Cross-site scripting)
			- Because it can be accessed by any JS

**Best practices:** 
- Use cookies for storing [[Express - Auth|auth tokens]]
	- Store access token (short-lived) in `HttpOnly` cookie
	- Optional: Store refresh token in `HttpOnly` + `Secure` cookie
	- Backend reads tokens from cookie → no JavaScript access = safer

# References

