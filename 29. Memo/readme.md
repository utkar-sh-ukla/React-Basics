# Memo

When a component is wrapped in `React.memo()`, React renders the component and memoizes the result. Before the next render, if the new props are the same, React reuses the memoized result `skipping the next rendering`.

### Folder Structure
```
components
    +|__MemoComp
```

### ParentComp

```js
...
import MemoComp from './MemoComp'

class ParentComp extends Component{
  ...
  render(){
    console.log('*****Parent Component render*****')

    return(
      <div>
        Parent Component
        <MemoComp name = {this.state.name} />
      </div>
    )
  }
}

...
```

### MemoComp

```js
import React from 'react'

function MemoComp({name}) {
  console.log('*****MemoComp rendered*****')
  return(
    <div>
      Memo Component {name}
    </div>
  )
}

export default React.memo(MemoComp)
```

### Console
![Untitled design](https://user-images.githubusercontent.com/61664827/137585821-3fd39371-9a59-47d8-b048-4beada82d80d.png)

