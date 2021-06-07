
##  State and Props


# Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’? 
the render hallens first then ‘componentDidMount

# What is the very first thing to happen in the lifecycle of React?
mounting -> when an instnce is created (constructor)


# Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates
constructor,  render , componentDidMount ,  React Updates , componentWillUnmount,


# What does componentDidMount do?
>This method is invoked immediately after a component is mounted


-----------------------------------------------------------------------------------------------------

# What types of things can you pass in the props? 
- pass values from a parent component down to a child component (string, object, numbers)
- use props to display things 
* props -> its like argument to function 

# What is the big difference between props and state?
1. props: pass it to the component (updated outside the component) 
2. state: it's inside the component (updated inside the component)

# When do we re-render our application?
when state change 


# What are some examples of things that we could store in state?
- if we want to change somethings we store it in the state (re-render / update)
- its useful inside form to know what change 



# Resources 
1. [React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI) 
2. [React: Component Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093) 
