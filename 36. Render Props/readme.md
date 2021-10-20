# Render Props

The term `render prop` refer to a technique for sharing code between React components using a prop whose value is a function.

### Folder Structure
```
components
    +|__CounterTwo.js
    +|__ClickCounterTwo.js
    +|__HoverCounterTwo.js
```

### App
```js
import './App.css';
import CounterTwo from './components/CounterTwo'
import ClickCounterTwo from './components/ClickCounterTwo'
import HoverCounterTwo from './components/HoverCounterTwo'

function App() {
  return (
    <div className="App">
      <CounterTwo>
        {(count, incrementCount) => (<ClickCounterTwo count={count} incrementCount = {incrementCount}/>)}
    </CounterTwo>
    <CounterTwo>
        {(count, incrementCount) => (<HoverCounterTwo count={count} incrementCount = {incrementCount}/>)}
    </CounterTwo>
    </div>
      );
    }
    
    export default App;
```

### CounterTwo
```js
import React, {Component} from 'react'

class CounterTwo extends Component {
  constructor(){
    super()
    this.state = {
      count: 0
    }
  }
  incrementCount = () => {
    this.setState((prevState) => {
      return {count: prevState.count + 1}
      })
  }

  render(){
    return (
        <div>
          {this.props.children(this.state.count, this.incrementCount)}
        </div>
    )
  }
}

export default CounterTwo
```

### ClickCounterTwo
```js
import React, {Component} from 'react'

class ClickCounterTwo extends Component {

  render(){
    const {count, incrementCount} = this.props
    return <button onClick = {incrementCount}> {this.props.name}  Clicked {count} times </button>
  }
}

export default ClickCounterTwo
```

### HoverCounterTwo
```js
import React, {Component} from 'react'

class HoverCounterTwo extends Component {

  render(){
    const {count, incrementCount} = this.props
    return <h2 onMouseOver = {incrementCount}> Clicked {count} times </h2>
  }
}

export default HoverCounterTwo
```
