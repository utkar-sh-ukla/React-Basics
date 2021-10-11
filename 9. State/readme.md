#   State

State is a plain JavaScript object used by React to represent an information about the component’s current situation.
-   State belongs to an individual component.
-   State is private to a component.
-   State should only be used when you need data about a component to change.

### Folder Structure
```
components
    +|__Message.js
```



### Message

```js
import React, {Component} from 'react'

class Message extends Component {
  constructor(){
    super()
    this.state = {
      message: "Welcome visitor"
    }
  }

  changeMessage(){
    this.setState({
      message: "Thankyou for subscribing"
    })
  }
  
  render(){
    return (
      <div>
        <h1> {this.state.message} </h1>
        <button onClick = {() => {this.changeMessage()}}> subscribe </button>
      </div>
    )
  }
}

export default Message
```

>   **Super()** : It is used to call the constructor of its parent class. This is required when we need to access some variables of its parent class.

>   When you pass `props` to `super`, the props get assigned to `this`. 

```js
...
constructor(props) {
    super();
    console.log(this.props) //undefined
}
...
```

```js
...
constructor(props) {
    super(props);
    console.log(this.props) //props will get logged.
}
...
```