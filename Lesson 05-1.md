## Outcomes  
- Identify what a Promise is in JavaScript
- Call APIs using fetch with .then and .catch
- Understand that code after the fetch is executed immediately, not after the fetch happens.
- Call APIs from React components when events happen (e.g. a click)
- Store the result of an API call in state

## Promises
Much like real life promises are a contract that can either be fuffiled or rejected. Promises are used when there is an action that will take an unkown amount of time, they allow us to not have to pause our code and wait until they are done. 

A common use case for promises and the one that this lesson will cover is using it with fetch to create api calls

## Calling apis 
There are many ways to call apis in javascript but the main way we are going to be doing it is by using the inbuilt fetch functionality 

```js
const fetchWeather = () => {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=Sydney&units=metric&appid=${APIKey}`;
  const foo = fetch(url);
  console.log(foo); // foo is a Promise
};
```

as you can see here foo is a promise, in order to use it we need to wait for it to be resolved 

in order to resolve the promise we can use the .then method

```js
const fetchWeather = () => {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=Sydney&units=metric&appid=${APIKey}`;
  fetch(url).then((response) => {
    console.log(response);
  });
};
```

here you can see that we have used the .then method, this gives us the data but we still need to process it by using the .json() method, this method also returns a promise so we can use another .fetch method

```js
const fetchWeather = () => {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=Sydney&units=metric&appid=${APIKey}`;
  fetch(url).then((response) => {
    console.log(response);
    response.json().then((jsonData) => {
      console.log(jsonData);
    });
  });
};
```

## catching failed promises
We have talked about how to handle sucessful promises but what happens when a promise fails? thats where catch comes in

using the .catch() method we can write what to do when a promise fails

```js
const fetchWeather = () => {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=Sydney&units=metric&appid=${APIKey}`;
  fetch(url).then((response) => {
    console.log(response);
    response.json().then((jsonData) => {
      console.log(jsonData);
    });
  }).catch(() => {
    console.log("something has failed")
  });
};
```