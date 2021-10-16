# Forwarding Refs

Ref forwarding is a technique for automatically passing a ref through a component to one of its children. This is typically not necessary for most components in the application. However, it can be useful for some kinds of components, especially in reusable component libraries. 

### Folder Structure

```
components
    +|__FRInput.js
    +|__FRParentInput.js
```

### FRParentInput
```js
import React, {Component} from 'react'
import FRInput from './FRInput'

class FRParentInput extends Component{
  constructor(props){
    super(props)
    this.inputRef = React.createRef()
  }
  
  clickHandler = () => {
    this.inputRef.current.focus()
  }

  render(){
    return(
      <div>
        <FRInput ref = {this.inputRef} />
        <button onClick={this.clickHandler}>Focus Input</button>

      </div>
    )
  }
}

export default FRParentInput
```

### FRInput
```js
import React from 'react'

const FRInput = React.forwardRef((props, ref) => {
  return(
    <div>
      <input type='text' ref = {ref} />
    </div>
  )
})

export default FRInput
```

