# Refs with Class Component

### Folder Structure
```
components
    +|__Input.js
    +|__FocusInput.js
```

### Input 

```js
import React, {Component} from 'react'

class Input extends Component{
  constructor(props){
    super(props)
    this.inputRef = React.createRef()
  }
  
  focusInput(){
    this.inputRef.current.focus()
  }

  render(){
    return(
      <div>
        <input type='text' ref = {this.inputRef} />
      </div>
    )
  }
}

export default Input
```

### FocusInput
```js
import React, {Component} from 'react'
import Input from './Input'

class FocusInput extends Component{
  constructor(props){
    super(props)
    this.componentRef = React.createRef()
  }
  
  clickHandler = () => {
    this.componentRef.current.focusInput()
  }

  render(){
    return(
      <div>
        <Input ref = {this.componentRef} />
        <button onClick={this.clickHandler}>Focus Input</button>

      </div>
    )
  }
}

export default FocusInput
```