2025-06-24 13:32

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - Routing

**Client side routing:** Allow you to build single page applications that simulate multi-page applications
- The links aren’t sent to the server (intercepted by JS) → browser never reloads
	- Instead, the page just simulates the change
- Problems:
	- Need to notify screen readers manually of screen change
	- ==Doable with libraries== 

**React router:** a lot of manual work
- Manually import and configure `react-router-dom`
- Define your routes using `<Route path="..." element={...} />`
- Use nested `<Routes>` or dynamic route parameters
- Manage a central router config file manually
- Learn more:
	- https://www.theodinproject.com/lessons/node-path-react-new-react-router 

**Next.js routing:** file system based routing (much simpler)
- Use folders + `page.js` to route to different pages
- Use square brackets for dynamic routes
	- `/blog/[slug]/page.js → /blog/my-post` 
	- **slug:** human-readable, URL-friendly part of a web address that identifies a particular page or resource
			- Called slug because it is like a *slug line* in journalism
- **For conditional rendering:**
	- Use `useEffect` and `router.push` (client) OR `redirect` (server - slower but more secure)


# References

