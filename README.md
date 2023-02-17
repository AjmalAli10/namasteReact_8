# namasteReact_8

## How do we create Nested Routes cofiguration with the help of react-router-dom library of version 6 and above?
### First Of all, What do we mean by nested routes?
> *`www.domain.com/about/profile` - Here `profile` is routed nestedly.*
### To make a nested routes 
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
### The Order of life Cylce in Class Based Components happend in Two Phase

### But On Mounting it will act diffrent same as for Updating and unMountig

### Mounting
 > *1 Render Phase* 
 #### 1. Constructor
 #### 2. render() method
 > *2 Commit Phase*
 #### DOM get updated
 #### 1. ComponentDidMount
 
 ### Updating
  > *1 Render Phase*
 #### 1. on State or props `Render method`get called
  >
  
  > *2 Commit Phase*
 #### DOM get updated
 #### 1. componentDidUpdate()
 
 ### UnMounting 
  > *1 Render Phase* 
  #### Nothing happend
  >
  >*2 Commit Phase*
  #### 1. componentWillUnmount()
## Why do we use componentDidMount?
### If the requirment is that after first render I want to mount or display somthing. In this case we use `componentDidMount()`

## Why do we use componentWillUnmount? Show with example
### It is use for cleanUp But what types of cleanup!  Let's UnderStand
> For example - After First Render you want to use timer which updating every second in your componentDidMount()
```
componentDidMount(){
  this.timer = setInterVal(()=>{
    console.log("Timer")
  }, 1000)
}
If We Will Not cleanup this on nevegating to diffrent component it will update every second.
eventhough if you are not on component that you have setted the setInterval
>
To Avoid this we will need to clean up the mess on componentWillUnmount()
componentWillUnmount(){
 clearInterval(this.timer)
}

```
