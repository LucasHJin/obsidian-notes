2025-06-27 22:33

Status:


Tags:
[[cs]] 
[[webdev]] 
[[mobile dev]] 


___________________________________________________________________________
# MVC explained

Stands for **Model - View - Controller** 
- A design pattern used to organize code in web applications by separating concerns

**Model:** holds and manages data and logic: saving, fetching, updating, validating
- Like the brain of the app
- Doesn’t have a set syntax (i.e. can be function, class, ORM, etc.)

**View:** Responsible for displaying data (HTML, React, etc.)
- I.e. the server side rendered HTML or JSON responses

**Controller:** Handles user input and routes (==bridge between model and controller==)
- Processes requests, talks to the model, and sends back the view (or JSON)

**Analogy:** it’s like a restaurant
- Model → Kitchen (has data + logic)
	- Can prepare food regardless of who ordered it
- Controller → Waiter (middleman)
	- Takes your order, returns to kitchen, brings food
	- Just coordinate everything happening
- View → The table presentation (UI)
	- The food the user gets (HTML, JSON, rendered page, etc.)


# References

