# Refs

Refs provide a way access and manipulate DOM nodes and React elements , directly.

### When to use Refs

There are a few good use cases for refs:
- Managing focus, text selection, or media playback.
- Triggering imperative animations.
- Integrating with third-party DOM libraries.

### Folder Structure
```
components
    +|__RefsComp.js
```
##  RefsComp

### Approach 1

```js
import React, {Component} from 'react'

class RefsComp extends Component{
  constructor(props){
    super(props)
    this.inputRef = React.createRef()
  }
  
  componentDidMount(){
    this.inputRef.current.focus()
    console.log(this.inputRef)
  }

  clickHandler = () => {
    alert(this.inputRef.current.value)
  }
  
  render(){
    console.log('*****Parent Component render*****')

    return(
      <div>
        <input type='text' ref = {this.inputRef} />
        <button onClick={this.clickHandler}>Click</button>
      </div>
    )
  }
}

export default RefsComp
```

### Approach 2 (Callback Ref)
```js
import React, {Component} from 'react'

class RefsComp extends Component{
  constructor(props){
    super(props)
    this.inputRef = React.createRef()
    this.cbRef = null
    this.setCbRef = element => {
      this.cbRef = element
    }
  }
  
  componentDidMount(){
    if(this.cbRef) {
      this.cbRef.focus()
    }
  }

  clickHandler = () => {
    alert(this.inputRef.current.value)
  }
  
  render(){
    console.log('*****Parent Component render*****')

    return(
      <div>
        <input type='text' ref = {this.setCbRef} />
        <button onClick={this.clickHandler}>Click</button>
      </div>
    )
  }
}

export default RefsComp
```