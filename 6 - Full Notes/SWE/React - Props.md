2024-09-26 13:49

Status:


Tags:
[[cs]]
[[webdev]]


___________________________________________________________________________
# React - Props

**Props:** mechanism for passing data and event handlers from one component to another in a React application
- Arguments that are passed into components
	- Is one-way (from parent to child)

Just pass all the attributes you want to the component and then accept as props/destructure
- 

**Common practices:** 
1. **Default props**
	1. Default values/fallback values for the props
	2. THIS IS NO LONGER USEFUL → use default parameters instead
```js
ChildComponent.defaultProps = {
    message: 'Default Message'
};
```
2. **[[React - PropTypes|PropTypes]]**  
	1. Enforce type of prop for debugging
```js
import PropTypes from 'prop-types';

ChildComponent.propTypes = {
    message: PropTypes.string.isRequired
};
```
3. **Functions as Props**
	1. You can pass functions as props to handle events in child components
	2. Don’t pass with the parentheses (will make the function run on render)
		1. If need to use parentheses → `() => fxn()` use anonymous function
```js
const ParentComponent = () => {
    const handleClick = () => {
        console.log('Button clicked!');
    };

    return <ChildComponent clicked={handleClick} />; 
};

const ChildComponent = ({ clicked }) => {
    return <button onClick={clicked}>Click Me</button>; 
}; //onClick event handler
```
4. **Destructuring**
	1. Destructure props for easier access
	2. Extracting and assigning values to variables
```js
const ChildComponent = ({ message }) => {
    return <div>{message}</div>;
};
```

**Alternative:** Use typescript for prop types and default values 
- [[Typescript explained]] 


# References

