# Form Handling

We know that HTML elements like input remember what we type. Similarly, we can use the React component state to store data of forms. When the input data of forms elements is handled by the React component, it’s called a Controlled Component. Here, the only source of truth is a component state, not a DOM element.

### Folder Structure

```
components
    +|__Form.js
```

### Form
```js
import React, {Component} from 'react'

class Form extends Component{
  constructor(){
    super()
    this.state = {
      username: '',
      comments: '',
      topic: 'react'
    }
  }

  handleUsernameChange = (event) => {
    this.setState({
      username: event.target.value
    })
  }

  handleCommentsChange = (event) => {
    this.setState({
      comments: event.target.value
    })
  }

  handleTopicChange = (event) => {
    this.setState({
      topic: event.target.value
    })
  }

  handleSubmit = (event) => {
    alert(`${this.state.username} ${this.state.comments} ${this.state.topic}`)

    event.preventDefault()
  }
  render(){
    return(
      <form onSubmit = {this.handleSubmit}>
      
        <div>
          <label> username </label>
          <input type='text' value = {this.state.username} onChange = {this.handleUsernameChange}/>
        </div>

        <div>
          <label> comments </label>
          <textarea value = {this.state.comments} onChange = {this.handleCommentsChange}/>
        </div>
        
        <div>
          <label>topic</label>
          <select value = {this.state.topic} onChange = {this.handleTopicChange}>
            <option value = 'react'> React </option>
            <option value = 'angular'> Angular </option>
            <option value = 'vue'> Vue </option>
          </select>
        </div>
        
        <button type = 'submit'> submit </button>
        
      </form>
    )
  }
}

export default Form
```
