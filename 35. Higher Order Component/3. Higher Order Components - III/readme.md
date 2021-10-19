# Higher Order Components - III

##  Passing down `props`

### App
```js
...
    <ClickCounter name= 'Alice'/>
    <HoverCounter />
...
```

### ClickCounter
```js
...
return <button onClick = {incrementCount}> {this.props.name}  Clicked {count} times </button>
...
```

### withCounter
```js
...
return(
        <WrappedComponent count={this.state.count} incrementCount={this.incrementCount} {...this.props}/>
      )
...
```

##  Passing parameter to H.O.C

### withCounter
```js
...
const withCounter = (WrappedComponent, incrementNumber) => {...}
...
```

### ClickCounter
```js
...
export default withCounter(ClickCounter, 5)
...
```

### HoverCounter
```js
...
export default withCounter(HoverCounter, 10)
...
```
