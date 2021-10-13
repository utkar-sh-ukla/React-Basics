# Event Handling

> `Event Handler` is a `function` & **not** a `function Call` so don't add paranthesis.



### Event Handling in Functional Components

####  Folder Structure

```
components
  +|__FunctionClick.js
```

####  FunctionClick

```js
import React from 'react'

function FunctionClick() {
  function clickHandler(){
    console.log('clicked !')
  }
  return (
    [+ <button onClick = {clickHandler()} >Click me !</button> +]
    <button onClick = {clickHandler} >Click me !</button>
  )
}

export default FunctionClick
``
