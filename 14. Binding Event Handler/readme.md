# Binding Event Handlers

- This is not something we need to do because of the way React works or because of JSX. This is because of the way the `this` binding works in JavaScript.

### Folder Structure

```
components
    +|__EventBinder.js

```

####  Event Binding in Class components

####  Approach 1

```js
import React, {Component} from 'react'

class EventBinder extends Component {
  constructor(){
    super()
    this.state = {
      message: "Hello, Visitor 🙏🏻"
    }
  }

  changeMessage(){
    this.setState({
      message: "GoodBye 🙋🏻‍♂️"
    })
    console.log(this)
  }

  render(){
    return (
      <div>
        <h1> {this.state.message} </h1>
        <button onClick = {this.changeMessage.bind(this)}> Click me ! </button>
      </div>
    )
  }
}

export default EventBinder
```

####  Approach 2

```js
import React, {Component} from 'react'

class EventBinder extends Component {
  constructor(){
    super()
    this.state = {
      message: "Hello, Visitor 🙏🏻"
    }
  }

  changeMessage(){
    this.setState({
      message: "GoodBye 🙋🏻‍♂️"
    })
    console.log(this)
  }

  render(){
    return (
      <div>
        <h1> {this.state.message} </h1>
        <button onClick = {() => {this.changeMessage()}}> Click me ! </button>
      </div>
    )
  }
}

export default EventBinder
```

####  Approach 3

```js
import React, {Component} from 'react'

class EventBinder extends Component {
  constructor(){
    super()
    this.state = {
      message: "Hello, Visitor 🙏🏻"
    }
    this.changeMessage = this.changeMessage.bind(this)
  }

  changeMessage(){
    this.setState({
      message: "GoodBye 🙋🏻‍♂️"
    })
    console.log(this)
  }

  render(){
    return (
      <div>
        <h1> {this.state.message} </h1>
        <button onClick = {this.changeMessage}> Click me ! </button>
      </div>
    )
  }
}

export default EventBinder
```

####  Approach 4

```js
import React, {Component} from 'react'

class EventBinder extends Component {
  constructor(){
    super()
    this.state = {
      message: "Hello, Visitor 🙏🏻"
    }
  }

  changeMessage = () => {
    this.setState({
      message: "GoodBye 🙋🏻‍♂️"
    })
    console.log(this)
  }

  render(){
    return (
      <div>
        <h1> {this.state.message} </h1>
        <button onClick = {this.changeMessage}> Click me ! </button>
      </div>
    )
  }
}

export default EventBinder
```