#   setState()

-   Always make use of setState & never modify the state directly.
-   Code has to be executed after the state has been updated ? Place the code in the callback function which is the second argument to this setState method.
-   When you have to upadate state based on the prevState, pass in a function as an Argument of the regular object.


### Folder Structure

```
components
    +|__Counter.js
```

### Counter

```js
import React, {Component} from 'react'

class Counter extends Component {
  constructor(){
    super()
    this.state = {
      count: 0
    }
  }
  increment() {
    
    //  can't modify state directly  
    // this.state.count = this.state.count + 1

    // this.setState({
    //   count: prevState.count + 1
    // },
    //   () => {
    //       console.log('Callback Value' , this.state.count)
    //   }
    // )

    this.setState((prevState) => ({
      count: prevState.count + 1
      }))
    console.log(this.state.count)
  }

  incrementFive(){
    this.increment()
    this.increment()
    this.increment()
    this.increment()
    this.increment()
  }
  render(){
    return (
        <div>
          <div> Count - {this.state.count} </div>
          <button onClick = {() => this.incrementFive()}> increment </button>
        </div>
    )
  }
}

export default Counter
```