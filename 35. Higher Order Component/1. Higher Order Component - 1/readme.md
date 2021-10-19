# Higher Order Components - I

### Folder Structure
```
components
    +|__ClickCounter.js
    +|__HoverCounter.js
```

### ClickCounter
```js
import React, {Component} from 'react'

class ClickCounter extends Component {
  constructor(){
    super()
    this.state = {
      count: 0
    }
  }

  incrementCount = () => {
    this.setState((prevState) => {return {
      count: prevState.count + 1}
    })
  }

  render(){
    const {count} = this.state
    return <button onClick = {this.incrementCount}> Clicked {count} times </button>
  }
}

export default ClickCounter
```

### HoverCounter
```js
import React, {Component} from 'react'

class HoverCounter extends Component {
  constructor(){
    super()
    this.state = {
      count: 0
    }
  }

  incrementCount = () => {
    this.setState((prevState) => {return {
      count: prevState.count + 1}
    })
  }

  render(){
    const {count} = this.state
    return <h2 onMouseOver = {this.incrementCount}> Clicked {count} times </h2>
  }
}

export default HoverCounter
```