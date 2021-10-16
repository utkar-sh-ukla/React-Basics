# Pure Components

A pure Component implements `shouldComponentUpdate()` with a `shallow prop & states` comparison.

> Shallow comparison means that when comparing objects, Javascript does not compare their’s attributes - only their references (e.g. “do they point to same object?).

### Regular Component vs Pure Component

|Regular Component|Pure Component|
|---|---|
|A Regular Component does not implements the `shouldComponentUpdate()` method. It always return true by default.|A Pure Component on the other hand implements `shouldComponentUpdate()` with a shallow props & states comparison|


### Folder Structure
```
components
    +|__ParentComp
    +|__PureComp
    +|__RegualarComp
```

### ParentComp

```js
import React, {Component} from 'react'
import RegularComp from './RegularComp'
import PureComp from './PureComp'

class ParentComp extends Component{
  constructor(props){
    super(props)
    this.state = {
      name : 'Henry'
    }
  }
  
  componentDidMount(){
    setInterval(() => {
      this.setState({
        name: 'Henry'
      })
    }, 2000)
  }
  
  render(){
    console.log('*****Parent Component render*****')

    return(
      <div>
        Parent Component
        <RegularComp name = {this.state.name} />
        <PureComp name = {this.state.name} />
      </div>
    )
  }
}

export default ParentComp
```

### PureComp

```js
import React, {PureComponent} from 'react'

class PureComp extends PureComponent{
  render(){
    console.log('*****Pure Component render*****')
    return(
      <div>
        Pure Component {this.props.name}
      </div>
    )
  }
}

export default PureComp
```

### RegularComp

```js
import React, {Component} from 'react'

class RegularComp extends Component{
  render(){
    console.log('*****Regular Component render*****')
    return(
      <div>
        Regular Component {this.props.name}
      </div>
    )
  }
}

export default RegularComp
```

### Console

![Untitled ](https://user-images.githubusercontent.com/61664827/137583859-4ef54eb4-19b2-4af8-a34a-17c10b8fde3b.png)


> If we Make Parent Component Pure than shallow comparison will also work on the child components.
