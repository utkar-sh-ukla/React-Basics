# Conditional Rendering 

Conditional rendering in React works the same way conditions work in JavaScript.

### Folder Structure

```
components
    +|__UserGreeting.js
```

### Approach 1 **(if-else)**

```js
import React, {Component} from 'react'

class UserGreeting extends Component{
  constructor(props){
    super(props)
    this.state = {
      isLoggedIn : false
    }
  }

  render(){
    if(this.state.isLoggedIn){
      return <h1> You are Logged In </h1>
    }
    else{
      return <h1> You are Logged Out </h1>
    }
  }
}

export default UserGreeting
```

### Approach 2 **(Element Variable)**

```js
import React, {Component} from 'react'

class UserGreeting extends Component{
  constructor(props){
    super(props)
    this.state = {
      isLoggedIn : false
    }
  }

  render(){
    let message
    if(this.state.isLoggedIn){
      message =  <h1> You are Logged In </h1>
    }
    else{
      message =  <h1> You are Logged Out </h1>
    }
    return <div> {message} </div>
  }
}

export default UserGreeting
```

### Approach 3 **(Ternary Condition)**

```js
import React, {Component} from 'react'

class UserGreeting extends Component{
  constructor(props){
    super(props)
    this.state = {
      isLoggedIn : false
    }
  }

  render(){
    return (this.state.isLoggedIn) ?  <h1> You are Logged In </h1> : <h1> You are Logged Out </h1>
  }
}

export default UserGreeting
```

### Approach 4 **(Short Circuit Operator)**

```js
import React, {Component} from 'react'

class UserGreeting extends Component{
  constructor(props){
    super(props)
    this.state = {
      isLoggedIn : true
    }
  }

  render(){
    return (this.state.isLoggedIn) &&  <h1> You are Logged In </h1> 
  }
}

export default UserGreeting
```

