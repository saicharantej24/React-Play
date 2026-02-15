# React-Play
# Functional components
# App.js
```js
import logo from './logo.svg';
import './App.css';
import Demo from './components/func';
import { Component } from 'react';

class App extends Component
{
  render()
  {
    return (
      <div className="App">
        <Demo/>
      </div>
    )
  }
}

export default App;
```
# func.js:
```js
import React from 'react';

// function Demo()
// {
//    return <h1>sai charan tej bsct</h1>
// }

const Demo=()=> <h1>sai charan tej bhogapurapu</h1>
export default Demo;
```
```text
We can import and export in diff way:
Export like this:
export const Demo=()=> <h1>sai charan tej bsct bhogapurapu</h1>
Import like this:
import {Demo} from './components/func';
```
# Class Components:
# Classcomp.js:
```js
import React,{Component} from 'react';

class Classcomp extends Component{
    render()
    {
        return <h1>Class comp</h1>
    }
}
export default Classcomp;
```
# Props:
# App.js
```js
import logo from './logo.svg';
import './App.css';
import {Demo} from './components/func';
import { Component } from 'react';

class App extends Component
{
  render()
  {
    return (
      <div className="App">
        <Demo name="sai"/>
        <Demo name="charan"/>
        <Demo name="tej"/>
      </div>
    )
  }
}

export default App;
```
# func.js:
```js
import React from 'react';
export const Demo=(props)=>{ 
return (
<div>
<h1>sai charan tej bsct bhogapurapu</h1>
<h1>Hi {props.name}</h1>
</div>
)
}
```
# React life cycle method:
# App.js:
```js
import logo from './logo.svg';
import './App.css';
import Classcomp from './components/Classcomp';
import Timer from './components/timer';
function App() {
  return (
    <div className="App">
    <Timer/>
    </div>
  );
}

export default App;
```
# timer.js:
```js
import React from 'react';

class Timer extends React.Component{
    constructor(props)
    {
        super(props);
        this.state={seconds:0};

    }
   componentDidMount(){
        this.interval=setInterval(()=>
        {
            this.setState(prevState=>({
                seconds:prevState.seconds+1
            })
        );
            },1000);
        }
        componentDidUpdate(prevProps,prevState)
        {
            if(prevState.seconds!=this.state.seconds)
            {
                console.log('seconds updated: ${this.state.seconds}');
            }
        }
        componentWillUnmount()
        {
            clearInterval(this.interval);
        }
   render()
   {
    return(
        <div>
            Seconds: {this.state.seconds}
        </div>
    )
   }
}
export default Timer;
```
# useEffect Hook:
# App.js:
```js
import logo from './logo.svg';
import './App.css';
import Hookuse from './components/Hookuse';
//import UseEffhook from './components/useEffhook';
import Timer from './components/timer';
function App() {
  return (
    <div className="App">
    <Hookuse />
    </div>
  ); 
}

export default App;

```
# Hookuse.js:
```js
import React,{useState,useEffect} from 'react';
function Hookuse()
{
    const[seconds,setSec]=useState(0);
    useEffect(()=>{
        const interval=setInterval(()=>{
            setSec(prev=>prev+1);
        },1000);
        return()=> clearInterval(interval);
    },[]);

    useEffect(()=>
    {
        console.log('seconds updated:{seconds}');
    },[seconds]);
return (
    <div>
      Seconds: {seconds}
    </div>
  );
}
export default Hookuse;
```
import React,{useState,useEffect} from 'react';
function Hookmouse(){
    const[x,setX]=useState(0);
    const[y,setY]=useState(0);
    const logMousePosition=(e)=>
    {
        console.log('mouse event');
        setX(e.clientX);
        setY(e.clientY);
    }
  useEffect(()=>{
    window.addEventListener('mousemove',logMousePosition)
    return()=>{
        console.log('componentunmounting');
        window.removeEventListener('mousemove',logMousePosition);
    }
  },[])
  
    return(
        <div>
        Hooks X-{x} Y-{y}
        </div>
    )
    }
export default Hookmouse;
