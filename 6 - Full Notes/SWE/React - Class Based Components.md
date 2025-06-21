2025-06-19 21:31

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# React - Class Based Components

This is the structure of writing components before [[React - Components|functional components]] 
- Only for dealing with legacy code (don’t write it like this)
- Was when there was no way to manage state (i.e. with hooks) → more verbose

Example:

- `extends component` → inheriting from React’s component class
- `super` method → allows you to use props in context of `this` (referencing the class instance)
	- Reference props with `this.`
- `render` → used to display JSX
- define `state` in constructor
	- Use predefined `setState` 
- `bind` declared methods’ `this` to the class’ `this` 
```javascript
import { Component } from "react";

class ClassInput extends Component {
  constructor(props) {
    super(props);

    this.state = {
      todos: [],
      inputVal: "",
    };

    this.handleInputChange = this.handleInputChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleInputChange(e) {
    this.setState((state) => ({
      ...state,
      inputVal: e.target.value,
    }));
  }

  handleSubmit(e) {
    e.preventDefault();
    this.setState((state) => ({
      todos: state.todos.concat(state.inputVal),
      inputVal: "",
    }));
  }

  render() {
    return (
      <section>
        <h3>{this.props.name}</h3>
        <form onSubmit={this.handleSubmit}>
          <label htmlFor="task-entry">Enter a task: </label>
          <input
            type="text"
            id="task-entry"
            name="task-entry"
            value={this.state.inputVal}
            onChange={this.handleInputChange}
          />
          <button type="submit">Submit</button>
        </form>
        <h4>All the tasks!</h4>
        <ul>
          {this.state.todos.map((todo) => (
            <li key={todo}>{todo}</li>
          ))}
        </ul>
      </section>
    );
  }
}

export default ClassInput;
```



# References

