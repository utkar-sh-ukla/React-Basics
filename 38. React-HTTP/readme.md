# React - HTTP

![Untitled Diagram drawio](https://user-images.githubusercontent.com/61664827/138263199-c0569311-9792-46f5-afb4-a0432127485c.png)

### Setup
```
npm install axios
```
##  HTTP GET REQUEST

### File Structure
```
src
  +|__components
        +|__PostList.js
```

### PostList
```js
import React, {Component} from 'react'
import axios from 'axios'

class PostList extends Component {
  constructor(){
    super()
    this.state = {
      posts: [],
      errorMsg: ''
    }
  }

  componentDidMount() {
    axios.get('https://jsonplaceholder.typicode.com/posts')
    .then(response => { 
      console.log(response) 
      this.setState({posts: response.data}) 
    })
    .catch(error => {
      console.log(error)
      this.setState({errorMsg: 'Error retreiving data'})
    })
  }

  render(){
    const {posts, errorMsg} = this.state
    return(
      <div>
        List of Posts
        {
          posts.length ?
          posts.map(post => <div key={post.id}>{post.title}</div>)
          :null
        }
        {
          errorMsg ? <div> {errorMsg} </div> : null
        }
      </div>
    )
  }
}

export default PostList
```

### HTTP POST REQUEST

### File Structure
```
src
  |__components
      +|__PostForm.js
```

### PostForm
```js
import React, {Component} from 'react'
import axios from 'axios'

class PostForm extends Component {
  constructor(){
    super()
    this.state = {
      userId: '',
      title: '',
      body:''
    }
  }

  changeHandler = (e) => {
    this.setState({[e.target.name]: e.target.value})
  }

  submitHandler = (e) => {
    e.preventDefault()
    console.log(this.state)
    axios.post('https://jsonplaceholder.typicode.com/posts', this.state)
    .then(response => { 
      console.log(response) })
    .catch(error => {
      console.log(error)
    })
  }

  render(){
    const {userId, title, body} = this.state
    return(
      <div>
        <form onSubmit = {this.submitHandler}>
        <div>
          <input type='text' name='userId' value={userId} onChange={this.changeHandler}/>
        </div>        <div>
          <input type='text' name='title'  value={title} onChange={this.changeHandler}/>
        </div>        <div>
          <input type='text' name='body' value={body} onChange={this.changeHandler} />
        </div>
        <button type='submit'>Submit</button>
        </form>
      </div>
    )
  }
}

export default PostForm
```

![Screenshot (23)](https://user-images.githubusercontent.com/61664827/138266666-5bae12b5-2ed2-43b2-8ed2-c932452d3ded.png)

