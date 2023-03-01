<!-- @format -->

# Week 3 - Part 2

## Outcomes  
- Understand the benefit of immutable state objects and props
- Modify arrays and objects in ways that do not modify the original
- Feel comfortable using the spread operator [...array] and {...object} to shallow copy objects and arrays.

## The problem with mutable variables
Mutable varibles can lead to unexpected behaviour within our code. 

## The Spread Operator 
one way to avoid mutating our data is to make copies of them, an easy way to do this would be by using the spread operator, this can be used both for arrays an object.

```js
const numberArray = [1,2,3,4,5]

const numberArrayCopy = [...array]
```

The spread operator inserts all the values of the original array/data structure 

## Others ways to manipulate data
While making copies of our data is a good way to go about preventing mutability, another good way is to use the array methods that are provided by javascript the most common are 

- .map
- .filter
- .sort 

these methods return a copy of the array they are manipulating and therefore preventing mutation