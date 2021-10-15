# Component Mounting Lifecycle Code

### Folder Structure

```
components
    +|__LifecycleA.js
    +|__LifecycleB.js
```

### LifecycleA

```js
import React, {Component} from 'react'
import LifecycleB from './LifecycleB'

class LifecycleA extends Component {
  constructor(props){
    super(props)
    this.state = {
      name: 'Brian'
    }
    console.log('Lifecycle A constructor')
  }

  static getDerivedStateFromProps(props, state){
    console.log('Lifecycle A getDerivedStateFromProps')
    return null
  }

  componentDidMount(){
    console.log('Lifecycle A componentDidMount')
  }

  render(){
    console.log('Lifecycle A render')
    return(
      <div>
        <div>
          Lifecycle A
        </div>
        <LifecycleB />
      </div>
    )
  }
}

export default LifecycleA
```

### LifecycleB
```js
import React, {Component} from 'react'

class LifecycleB extends Component {
  constructor(props){
    super(props)
    this.state = {
      name: 'Brian'
    }
    console.log('Lifecycle B constructor')
  }

  static getDerivedStateFromProps(props, state){
    console.log('Lifecycle B getDerivedStateFromProps')
    return null
  }

  componentDidMount(){
    console.log('Lifecycle B componentDidMount')
  }

  render(){
    console.log('Lifecycle B render')
    return(
      <div>
        Lifecycle B
      </div>
    )
  }
}

export default LifecycleB
```

***
