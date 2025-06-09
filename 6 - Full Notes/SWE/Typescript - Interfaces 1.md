2025-06-06 22:15

Status:


Tags:
[[cs]]
[[webdev]]



___________________________________________________________________________
# Typescript - Interfaces

**`interface`:** a way to define the structure of an object (similar to `type`) 
```ts
interface User {
  name: string;
  age?: number; // optional
}

const user: User = {
  name: "Lucas",
  age: 18,
};
```
- Can extend other properties
- Can add `readonly` to make it immutable 
- Can add optional properties (not necessary)



# References
https://www.geeksforgeeks.org/what-is-interfaces-and-explain-it-in-reference-of-typescript/
