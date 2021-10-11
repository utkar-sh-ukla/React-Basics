#   Functional Components

```
Properties     -->    Javascript Function    --> HTML(JSX)
(props)
```

### Folder Structure

```
src
    +|__components
            +|__Greet.JSX
```

###    Greet

```js
import React from 'react'

function Greet() {
  return <h1>Hello React </h1>
}

export default Greet;
```

#### Using arrow Function

```js
import React from 'react'

const Greet = () => <h1> Hello React </h1>

export default Greet;
```
