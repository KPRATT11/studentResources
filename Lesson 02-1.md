<!-- @format -->

# Week 2 - Part 1

## Outcomes 
- be able to understand and use state and setState 
  
## State
Often times in our react applications we need to store values that will later change, this is where the concept of state comes in 

we can initialize state in our constructor method 
```js
class PushupCounter extends Component {
  constructor(props) {
    super(props);
    // Create initial state value
    this.state = { count: 0 };
  }
```

we can then modify the state by using the setState command

```js
this.setState({ count: this.state.count + 1 });
```

It is important to remember that the entire state will get set to whatever value you provide in the setState function. 