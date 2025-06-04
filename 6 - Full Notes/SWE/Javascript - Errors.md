2025-06-02 10:40

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Javascript - Errors

**Syntax error:** when the code you are trying to run is not written correctly
**Reference error:** when the variable you are trying to reference does not exist (within the current scope)
**Type error:** happens when:
- an operand or argument passed to a function is incompatible with the type expected by that operator or function;
- or when attempting to modify a value that cannot be changed;
- or when attempting to use a value in an inappropriate way.

**Try-catch block:** allows you to try something that might create an error and catch it before it crashes the program
- Can handle runtime errors in a better manner (useful for APIs, fetch, JSON)
```js
try {
  // code
} catch (error) {
  // handle error
} finally {
  // always runs, whether there's an error or not
}
```


# References

