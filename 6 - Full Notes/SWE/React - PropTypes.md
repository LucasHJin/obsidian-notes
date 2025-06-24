2025-06-23 15:12

Status:


Tags:
[[cs]]
[[webdev]]



___________________________________________________________________________
# React - PropTypes

Allows you to specify the type and default value for any properties you pass into your component

**Alternative:** Use [[Typescript explained|typescript]] 
I.e. you can define a `type` for your all props and destructure it
```ts
import React from 'react';

type MyComponentProps = {
  name: string;
  age?: number; // Optional prop
};

const MyComponent = ({ name, age = 18 }: MyComponentProps) => {
  return (
    <div>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
    </div>
  );
};

export default MyComponent;
```



# References

