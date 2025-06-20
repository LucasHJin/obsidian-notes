2024-09-26 13:31

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - useState

**State:** is a [[React - Hooks]] 
- Allows you to keep track of a variable's value within the virtual DOM
	- This means that it doesn't need to refresh everything and can just update that one variable by calculating difference between virtual and actual DOM
- Useful because local variables don’t persist between rerenders

**Updating a Variable's state:**
- Define the useState object (i.e. `const [name, setName] = useState('')`)
- Updating with [[React - Updater Functions]]:
	- `setName(prevName => prevName + lastName)`
- Updating with just value (when no need for previous reference):
	- `setName("Ben")`

**Updating an Object's state:**
- Define the useState object like normal (just with {} for the object)
- Use the spread operation (`setCar({...car, year: 2025})`)
- Use [[React - Updater Functions]] (so that you are referencing previous instance rather than new copy) 
	- i.e. `setCar(c => ({...c, year: event.target.value}))` -> c is first letter of state variable

**Updating an Array's state:**
- Define the useState array like normal (just with `[]` for the array)
- Same as the object
	- Use spread operator and updater function:
	- i.e. `setFoods(f => [...f, newFood]`
		- To delete an item -> filter for all items not equal to certain index using the above

**Updating an Array of Objects' state:** 
- Have one useState array defined with an array inside -> `useState([])` 
- Have useState variables for each one of the attributes of the object
- Create the object and then put it in useState array
	- I.e. `const newCar = {year: carYear, model: carModel}` 
	- `setCars(c => [...c, newCar]` 
- Removal is same as above
	- `setCars(c => c.filter((_, i) => i !=== index))` where index is passed in

# References

