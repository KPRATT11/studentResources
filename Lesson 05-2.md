## Outcomes  
- Understand how and when to use useEffect

## useEffect
useEffect is another common react hook, it allows you to perform side-effects or actions in your component when something changes 

the useEffect hook takes in 2 arguments
- a callback function
- a dependancy array

```js
useEffect(
    () => console.log("effect")
,[props])
```
This useEffect hook will console log the word effect everytime props changes

#### Callback function
The callback function is what will be called whenever the useEffect hook is run

#### Depenency array
The dependency array tells the useEffect hook when to run, any time one of the values inside of the useEffect hook changes the callback function will run

it is also important to note that if you have an empty dependancy array the callback will only run once, on mount 