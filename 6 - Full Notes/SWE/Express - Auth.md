2025-06-28 22:27

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Express - Auth

**Stateful vs Stateless Authentication:** 
- **Stateful** → session based 
	- A session is created when the user logs in and stored in memory, a DB or Redis
	- Session ID is sent to user (stored in a [[Cookies explained|cookie]]) 
	- In requests, browser sends cookie to server to use to look up user
	- *Pros:* 
		- Easy to revoke sessions (delete from DB)
		- Server has full control
	- *Cons:* 
		- Need centralized store (Redis) to scale
		- Requires server-side session management 
- **Stateless** → Token based (i.e. JSON Web Token - JWT)
	- A token with a signature is created when logged in and sent to the client (localStorage or cookie)
	- On request → the user sends it back in the `Authorization` header
	- The server verifies the token but ==never stores anything== 
	- *Pros:* 
		- Scales easily
		- Good for APIs (i.e. restful)
		- The user can interact with any server to authenticate
	- *Cons:* 
		- Harder to revoke tokens
		- Need to handle token expiration carefully
	- *NOTE:* Authentication ≠ Authorization
		- JWT is authorization → making sure same as the user that logged in

**Example** → Forum style app like reddit
- Use Next.js + Express + JWT (stateless)
	- Send a JWT token when logged in
	- Frontend can use `localStorage` or `httpOnly cookie` 
	- Verify using the token
- For JWT:
	- Auto-expire after a set time (exp)
	- Include user roles/permissions (role: 'admin')

*Note* → all verification should be done in backend (including if valid email, password, etc.) 

**Visual differences** 
![[Screenshot 2025-06-29 at 9.18.08 PM.png]]

# References

