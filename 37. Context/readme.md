# Context 

Context provides a way to pass data through the component tree without having to pass props down manually at every level.

### Folder Structure
```
components
    +|__userContext.js
    +|__ComponentC.js
    +|__ComponentE.js
    +|__ComponentF.js
```

### App
```js
import './App.css';
import ComponentC from './components/ComponentC'
function App() {
  return (
    <div className="App">
      <ComponentC/>
    </div>
      );
    }
    
export default App;
```

### ComponentC
```js
import React, {Component} from 'react'
import ComponentE from './ComponentE'

class ComponentC extends Component {
  render() {
    return <ComponentE />
  }
}

export default ComponentC
```

### ComponentE
```js
import React, {Component} from 'react'
import ComponentF from './ComponentF'

class ComponentE extends Component {
  render() {
    return <ComponentF />
  }
}

export default ComponentE
```

### ComponentF
```js
import React, {Component} from 'react'

class ComponentF extends Component {
  render() {
    return (
      <div>
        Component F
      </div>
    )
  }
}

export default ComponentF
```

##  Steps to create a Context API

### Crete the Context

####  userContext

```js
import React from 'react'

const UserContext = React.createContext()

const UserProvider = UserContext.Provider
const UserConsumer = UserContext.Consumer

export {UserProvider, UserConsumer}
```
### Provide a context 

#### App

```js
...
import {UserProvider} from './components/userContext'

function App() {
  return (
    <div className="App">
      <UserProvider value="Brady">
        <ComponentC/>
      </UserProvider>
    </div>
      );
    }
    
export default App;
```

### Consume the context value

####  ComponentF

```js
import React, {Component} from 'react'
import {UserConsumer} from './userContext'

class ComponentF extends Component {
  render() {
    return (
      <UserConsumer>
        {username => {
          return <div> Hello {username} </div>
        }}
      </UserConsumer>
    )
  }
}

export default ComponentF
```

##  Default value

####  App

```js
...
function App() {
  return (
    <div className="App">
      <ComponentC/>
    </div>
      );
    }
...
```

#### userContext

```js
....
const UserContext = React.createContext('Context API')
...
```

##  Context Type

#### userContext

```js
...

export default UserContext
```

### ComponentE
```js
...
import UserContext from './userContext'

class ComponentE extends Component {
  static contextType = UserContext
  render() {
    return (
      <div>
      Component E context {this.context}
      <ComponentF/>
      </div>
    )
  }
}

export default ComponentE
```

