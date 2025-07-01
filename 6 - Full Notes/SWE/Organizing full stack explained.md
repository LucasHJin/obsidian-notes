2025-06-29 20:02

Status:


Tags:



___________________________________________________________________________
# Organizing full stack explained

**Old way:** keep the data and view tightly coupled together (Server Side Rendering)
- Render the HTML in the backend → browser just displays what it receives
- Negatives → slower speed and less scalability
- I.e. EJS, Django

**New way:** separate the data and view → frontend and backend as well (called [Jamstack](https://jamstack.org/what-is-jamstack/))
- Get JSON in the backend → send to frontend to be rendered dynamically
- More modular + allows for using a single backend for multiple frontends (mobile, web, etc.)
- I.e. View, React
- [[APIs explained|How to implement]]

*General gist* → pass information with `res.json()` instead of `res.send()` / `res.render()` 
- [[Express - Routes]] 




# References

