# Event Handling

> `Event Handler` is a `function` & **not** a `function Call` so don't add paranthesis.



### Event Handling in Functional Components

####  Folder Structure

```
components
  +|__FunctionClick.js
```

####  FunctionClick

```diff
import React from 'react'

function FunctionClick() {
  function clickHandler(){
    console.log('clicked !')
  }
  return (
-     <button onClick = {clickHandler()} >Click me !</button> 
+     <button onClick = {clickHandler} >Click me !</button>
  )
}

export default FunctionClick
```

### Event Handling in Class Components

####  Folder Structure

```
components
  +|__ClassClick.js
```

####  ClassClick

```js
import React, {Component} from 'react'

class ClassClick extends Component {
  clickHandler(){
    console.log('clicked !')
  }
  render(){
    return(<button onClick = {this.clickHandler}>Click me ! </button>)
  }
}

export default ClassClick
```
