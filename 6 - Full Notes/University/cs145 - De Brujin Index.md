2025-11-25 11:06

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - De Brujin Index

**Usecase:** 
- [[cs145 - Building A λ-calculus Interpreter|Interpreter]] fails to deal with capture (can only do beta reduction, not alpha equivalence)
- Could try applying renaming but this will get complicated
- INSTEAD → use number systems
	- “How far away is the lambda that binds to me?“

**Examples:** 
- `λx.x is λ1` 
- `λy.y is λ1` 
- `λx. (λy. x) is λλ2` 
- Can draw AST for each
	- ![[Untitled_Artwork 26.png|500]] 
- `((λx. ((λf. x) y)) f)` 
	- ![[Untitled_Artwork 27.png|500]] 
- `((λλ1) (λ1)) (λλ2)` 
	- ![[Untitled_Artwork 28.png|500]] 
	- ![[Untitled_Artwork 29.png|500]] 
	- ![[Untitled_Artwork 30.png|500]] 
		- Go back through tree until you have encountered the number of abstractions desired
 





# References

