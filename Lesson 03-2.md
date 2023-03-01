<!-- @format -->

# Week 3 - Part 2

## Outcomes  
- Understand the lifecycle of a component, mainly when its updated
- Understand `componentDidMount()`, `componentDidUpdate()` and `componentWillUnmount()`

## The lifecycle of a component
Each component goes through 3 main *phases* 
- Mounting 
- Updating 
- Unmounting 

#### Mounting 
Mounting refers to the action of the component being placed in the dom, this happens when the component is first rendered / when the constructor() is first called

#### Updating
Updating reders to the action taken whenever something in the component changes/updates this can happen due to 
- state changes 
- prop changes 
- parent component rerendering

#### Unmounting 
Unmounting refers to the action of the component being removed from the dom, this happens whenever the component is no longer being rendered 


## Component lifecycle methods
There are 3 main methods that we can use related to the components life cycle methods 

#### componentDidMount()
This method gets called straight after the component has mounted, out of all life cycle methods this one tends to get used the most 

#### componentDidUpdate()
This gets called straight after a component has updated

### componentWillUnmount()
This gets called straight before a component unmounts    