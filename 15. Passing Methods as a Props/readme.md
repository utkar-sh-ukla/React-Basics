# Passing Methods as Props

### Folder Structure
```
components
    +|__ParentComponent.js
    +|__ChildComponent.js
```

### ParentComponent

```js
import React, {Component} from 'react'
import ChildComponent from './ChildComponent'

class ParentComponent extends Component {
  constructor(props){
    super(props)
      this.state = {
        parentName: 'Parent' 
      }
    this.greetParent = this.greetParent.bind(this)
  }

  greetParent(childName){
    alert(`Hello ${this.state.parentName} from ${childName}`)
  }
  
  render(){
    return(<div>
        <ChildComponent greetHandler = {this.greetParent}/>
    </div>)
  }
}

export default ParentComponent
```

### ChildComponent

```js
import React, {Component} from 'react'

function ChildComponent(props){
  return(
    <div>
      <button onClick = {() => {props.greetHandler('Child')}}>Greet Parent</button>
    </div>
  )
}

export default ChildComponent
```