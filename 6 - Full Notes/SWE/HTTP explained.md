2024-07-28 22:42

Status:
#finished

Tags:
[[cs]]
[[webdev]]

___________________________________________________________________________
# HTTP explained

**Hypertext Transfer Protocol:**
- Dominant protocol for transmitting data between clients and servers
	- Request-Response model
- Is **stateless** (each request is handled independent of any other request)
- Is used to implement [[REST explained |RESTful principles]]
	- Critical to RESTful [[APIs explained |APIs]]
- Has methods that can implement [[CRUD explained|CRUD]]

**Example body:**
```
{
  "name": "Sneakers",
  "color": "blue",
  "price": 59.95,
  "currency": "USD"
}
```

*NOTE: HTTP vs HTTPS*:
- HTTPS → HTTP Secure
	- Uses encryption (SSL/TLS) to protect the data transferred between your browser and the website
	- Prevents 
 

# References

https://blog.postman.com/what-are-http-methods 