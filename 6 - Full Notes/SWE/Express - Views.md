2025-06-27 21:12

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Express - Views

[[MVC explained|Important theory]] 
- *Note* → many modern apps only use Express (backend) for sending and receiving JSON and interacting with APIS
	- In this case → Views are redundant

**Views:** user-facing part of the application (HTML files / JSON)
- Use **template engines** to create views
	- Write template files → replaced with HTML + variables replaced with dynamic data

**Example:** [EJS](https://ejs.co/) 
- `<% and %>` → allow the use of javascript
- `<%= and %>` → variables
- Make `index.ejs` in `views` folder
- EJS has access to any properties from the object passed into `res.render` + `res.locals` 




# References

