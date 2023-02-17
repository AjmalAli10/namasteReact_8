# namasteReact_8

## How do we create a Nested Routes configuration with the help of the react-router-dom library of version 6 and above?
### First Of all, What do we mean by nested routes?
> *`www.domain.com/about/profile` - Here `profile` is routed nested.*
### To make nested routes 
#### We need to import `createBrowserRouter` to create any routes configuration.
```
import {createBrowserRouter} from react-router-dom;
import MainApp from "/MainApp";
import About from "./components/About;
import Profile from "./components/Profile;

cosnt router = createBrowserRouter([
{
  path: "/",
  element: <MainApp />,
  children: [
  {
    path: "/about",
    element: <About />,
    children: [
    {
      path: "profile",
      element: <Profile />
    }
    ]
  }
  ]
}
])
```
## What is the order of life cycle method calls in Class Based Components?
### The Order of life Cycle in Class Based Components happened in Two-Phase

### But On Mounting it will act different same as for Updating and unmounting

### Mounting
 > *1 Render Phase* 
 #### 1. Constructor
 #### 2. render() method
 > *2 Commit Phase*
 #### DOM gets updated
 #### 1. ComponentDidMount
 
 ### Updating
  > *1 Render Phase*
 #### 1. on State or props `Render method gets called
  >
  
  > *2 Commit Phase*
 #### DOM gets updated
 #### 1. componentDidUpdate()
 
 ### UnMounting 
  > *1 Render Phase* 
  #### Nothing happened
  >
  >*2 Commit Phase*
  #### 1. componentWillUnmount()
## Why do we use componentDidMount?
### If the requirement is that after the  render I want to mount or display something. In this case, we use `componentDidMount()`

## Why do we use componentWillUnmount? Show with example
### It is used for cleanUp But what types of cleanup?  Let's UnderStand
> For example - After First Render you want to use a timer which updates every second in your componentDidMount()
```
componentDidMount(){
  this.timer = setInterVal(()=>{
    console.log("Timer")
  }, 1000)
}
If We Will Not clean up this by navigating to the different components it will update every second.
even though you are not on the component that you have set the setInterval
>
To Avoid this we will need to clean up the mess on a component will unmount()
the component will unmount(){
 clearInterval(this.timer)
}

```
