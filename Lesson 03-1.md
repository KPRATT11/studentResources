<!-- @format -->

# Week 3 - Part 1

## Outcomes  
- Keeping state in a top level component while passing functions to child components with props 
- Understand why it's important for state to be controlled at the highest level 

## Props data types
props can be **any** data type

- Strings, numbers, booleans
- Arrays
- Objects
- Custom classes
- Functions

It is important to understand that functions can be passed as props as we will use that a lot 

## Keeping state in top level 
It is important to remember that we can **only** pass state down to children. A solution to this is to pass down functions as props and let those functions change the state

```js
  constructor(){
    super()
    this.state = {
      isClicked: false
    }
  }

  handleClick = () => {
    this.setState({
      isClicked: true
    }, () => console.log(this.state.isClicked))

  }
```
here you can see we have a handle click function, if we wanted a child component to be able to change the state we can pass the handle click function as a prop

```js
 <NewComponent clickMe={this.handleClick} />
```

here is what the child component looks like
```js
class NewComponent extends React.Component {

    clickMe = () => {
        this.props.clickMe()
    }

    render() {
        return (
            <div>
                <button onClick={this.clickMe}>Click Me!</button>
            </div>
        )
    }
} 
```

as we can see we are calling the function we passed in on the onClick event