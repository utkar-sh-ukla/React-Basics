# Error Boundaries

- Error boundaries are React components that catch Javascript error in their child component tree, log those errors, & display a fall-back UI.
- A class component becomes an error boundary by defining either or both of `getDerivedStateFromError` & `componentDidCatch` lifecycle methods.
- The placemenent of the Error Boundary also matters as it controls if teh entire app should have the fall-back UI or just the component causing the problem.
- Provide a way to gracefully handle error in application code.

### Folder Structure

```
components
    +|__Hero.js
    +|__ErrorBondary.js
```

### Hero

```js
import React from 'react'

function Hero ({heroName}) {
  if(heroName === 'Joker') {
    throw new Error('Not a hero!')
  }

  return (
    <h1>
      {heroName}
    </h1>
  )
}

export default Hero
```

### ErrorBondary

```js
import React, {Component} from 'react'

class ErrorBoundary extends Component {

  constructor(props) {
    super(props)

    this.state = {
      hasError: false
    }
  }

  static getDerivedStateFromError(error) {
    return {
      hasError: true
    }
  }

  componentDidCatch(error, info) {
    console.log(error)
    console.log(info)
  }

  render() {
    if(this.state.hasError){
      return <h1> Something went wrong 😟</h1>
    }
    return this.props.children
  }
}

export default ErrorBoundary 

```

