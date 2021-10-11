#   Class Components

```
Properties     -->    ES6 Class : state    --> HTML(JSX)
(props)
```

### Folder Structure

```
src
    |__components
            +|__Welcome.js
```

###    Welcome

```js
import React, {Component} from 'react'

class Welcome extends Component {
  render(){
    return <h1> Welcome React </h1>
  }
}

export default Welcome
```

