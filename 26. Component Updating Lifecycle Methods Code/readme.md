# Component Updating Lifecycle Methods Code

### LifecycleA

```js
import React, { Component } from 'react'
import LifecycleB from './LifecycleB'

class LifecycleA extends Component {
	constructor(props) {
		super(props)
		this.state = {
			name: 'Brian'
		}
		console.log('LifecycleA constructor')
	}

	static getDerivedStateFromProps(props, state) {
		console.log('LifecycleA getDerivedStateFromProps')
		return null
	}

	componentDidMount() {
		console.log('LifecycleA componentDidMount')
	}

	shouldComponentUpdate() {
		console.log('LifecycleA shouldComponentUpdate')
		return true
	}

	getSnapshotBeforeUpdate(prevProps, prevState) {
		console.log('LifecycleA getSnapshotBeforeUpdate')
    return null
	}

	componentDidUpdate(prevProps, prevState, snapshot) {
		console.log('LifecycleA componentDidUpdate')
	}

	changeState = () => {
		this.setState({
			name: 'Diana'
		})
	}

	render() {
		console.log('LifecycleA render')
		return (
			<div>
				<button onClick={this.changeState}>Change state</button>
				LifecycleA<LifecycleB />
			</div>
		)
	}
}

export default LifecycleA
```

### LifecycleB
```js
import React, { Component } from 'react'

class LifecycleB extends Component {

  constructor(props) {
    super(props)
    this.state = {
      name: 'Vishwas'
    }
    console.log('LifecycleB constructor')
  }

  static getDerivedStateFromProps(props, state) {
    console.log('LifecycleB getDerivedStateFromProps')
    return null
  }

  componentDidMount() {
    console.log('LifecycleB componentDidMount')
  }

  shouldComponentUpdate() {
    console.log('LifecycleB shouldComponentUpdate')
		return true
	}

	getSnapshotBeforeUpdate(prevProps, prevState) {
    console.log('LifecycleB getSnapshotBeforeUpdate')
    return null
	}

	componentDidUpdate(prevProps, prevState, snapshot) {
		console.log('LifecycleB componentDidUpdate')
	}

  render() {
    console.log('LifecycleB render')
    return (
      <div>
        LifecycleB
      </div>
    )
  }
}

export default LifecycleB

```

***

###	Before State Change
![Screenshot (15)](https://user-images.githubusercontent.com/61664827/137454770-73a037c9-c518-475d-9509-af62fe5867b7.png)

###	After State Change
![Screenshot (16)](https://user-images.githubusercontent.com/61664827/137454800-2efded0e-44da-4f1f-94ac-b59a05ceb7a9.png)
