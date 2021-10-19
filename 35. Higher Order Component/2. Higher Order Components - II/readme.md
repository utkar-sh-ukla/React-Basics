# Higher Order Components - II

A pattern when a function takes a component as an argument & return a new component

```
const NewComponent = higherOrderComponent(originalComponent)
const EnhancedComponent = higherOrderComponent(originalComponent)

e.g.  const IronMan = withSuit(Tony Stark) 
```

### Folder Structure
```
components
    +|__withCounter.js
```

### withCounter
```js
import React from 'react'

const withCounter = WrappedComponent => {
  class WithCounter extends React.Component {
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
    render() {
      return(
        <WrappedComponent count={this.state.count} incrementCount={this.incrementCount}/>
      )
    }
  }
  return WithCounter
}

export default withCounter
```

### ClickCounter
```js
import React, {Component} from 'react'
import withCounter from './withCounter'

class ClickCounter extends Component {

  render(){
    const {count, incrementCount} = this.props
    return <button onClick = {incrementCount}> Clicked {count} times </button>
  }
}

export default withCounter(ClickCounter)
```

### HoverCounter
```js
import React, {Component} from 'react'
import withCounter from './withCounter'

class HoverCounter extends Component {

  render(){
    const {count, incrementCount} = this.props
    return <h2 onMouseOver = {incrementCount}> Clicked {count} times </h2>
  }
}

export default withCounter(HoverCounter)
```
