<!-- @format -->

# Week 1 - Part 2

## Outcomes 
- Understand how to create both functional and class based React components 
- Understand the Virtual DOM and the reason for the `key={}` property 
- Be able to use conditional logic in React components
  

### Class components 
Class compenets can do the same thing as functional components for now we will focus on class components 
```js 
import { Component } from "react";

class Movie extends Component {
  render() {
    return <h2>{this.props.title}</h2>;
  }
}
```

##### Notes 
- We need to import `Component` from `"react"` 
- We need to extend our class with `Component` 
- The `render` method must be there, it is was actually renders our JSX
- We can acess props using `this.props` compared to just using `props` like we would in functional components 


### Displaying elements from an array
in order to display elements from an array we need to provide react with an array of react elements eg `[<div><div/>,<div><div/>]` 

The best way to go about this is using the `.map` function on the array

The `.map` function takes a function and runs that function for every element in an array.

[.map documentation](https://www.w3schools.com/jsref/jsref_map.asp)

### Conditional logic
Often times in our React apps we need to use conditional logic, becuase we can only write expression in the JSX we have to use something else.

a good alternative is the ternery operator 
[ternery operator documentation](https://www.w3schools.com/java/java_conditions_shorthand.asp)

[How to use ternary operator in react](https://codesource.io/how-to-use-ternary-operator-in-react/)