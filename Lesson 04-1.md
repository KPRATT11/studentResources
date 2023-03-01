<!-- @format -->

# Week 3 - Part 2

## Outcomes  
- Use useState hooks for storing state in function components
- Using multiple state values for separate pieces of state in function components

## Hooks 
In order to get some of the functionality that we had in class components within our functional components we need to use hooks

Hooks are special types of function that allow us to "hook" into react features

## useState hook
As the name says the useState hook allows us to use state in our functional components

it accepts one argument, this is the default state 

it returns an array, `[state, setState]` 
The first element in the array is the current state
The second element is a function we can use to set the state

when using the useState hook we normally use array destructuring to get these 2 values

```js
const [count, setCount] = useState(0)
```

in this example we have state storing a count that we set to 0 as default 

## multiple useStates
if we want multiple state values we can simply use multiple useState hooks

```js
const [count, setCount] = useState(0)

const [name, setName] = useState("John")
```

Here you can see we are using both a name and a count