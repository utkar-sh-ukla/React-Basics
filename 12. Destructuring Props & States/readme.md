# Destructuring State & Props

####  Destructuring in Functional Components

- I'st Method

```js
...
const Greet = ({name, heroName}) => {
  return(
  <h1> Greetings! {name} a.k.a {heroName}</h1>
  )
}
...
```

- II'nd Method

```js
...
const Greet = (props) => {
  const {name, heroName} = props
  return(
  <h1> Greetings! {name} a.k.a {heroName}</h1>
  )
}
...
```

####  Destructuring in Class Components

```js
...
class Welcome extends Component {
  render(){
    const {name, heroName} = this.props
    return <h1> Welcome {name} a.k.a {heroName}</h1>
  }
}
...
```