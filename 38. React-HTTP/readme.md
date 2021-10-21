# React - HTTP

![Untitled Diagram drawio](https://user-images.githubusercontent.com/61664827/138263199-c0569311-9792-46f5-afb4-a0432127485c.png)


### Setup
```
npm install axios
```

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
