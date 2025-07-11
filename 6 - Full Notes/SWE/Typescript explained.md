2025-06-06 22:00

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# Typescript explained

*Note:* very similar to [[Javascript Explained|Javascript]] 
- Main difference → is useful for error prevention because it catches them during compiling and you can define types for values
- **Is an OOP language** 
	- Adds classes with access modifiers (public, private, etc.)
	- Adds [[Typescript - Interfaces|interfaces]]
	- Adds abstract classes
	- Adds inheritance + polymorphism

**Static typing:** where variable types are known at compiling time
- Expressed explicitly by the user
- **Type annotation** → `: type` 
	- **BUT** → don’t always need to annotate type always (type inference → can infer the type)
		- ==Can’t change the type after it is infered== 
	- Also → you have angle brackets `<>` for type annotation of state
		- I.e. `const [data, setData] = useState<T | null>(null);` 
			- Can either be T or null
			- `T` is a generic placeholder value → want to be flexible but still have type safety

**Differences:** 
- **Variables** → add type annotation
- **Function** → define parameter and return types
	- `function f(a: number, b: number): number {...}` 
- **Objects** → define `type` (class) for the user before creating instances (objects) of the class
	- Instead of just creating the object/instance directly
- **Props in components** → define using a `type` (replaces PropTypes)
```ts
type ProfileProps = {
  name: string;
  age: number;
};

function Profile({ name, age }: ProfileProps) {
  return <h1>{name} - {age}</h1>;
}
```
- **Default values** → just add onto the end of the type annotation
	- `name: string = "Guest"` 



# References
https://www.geeksforgeeks.org/difference-between-typescript-and-javascript/ 
