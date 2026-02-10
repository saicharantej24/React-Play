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

