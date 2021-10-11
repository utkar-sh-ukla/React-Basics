#   Props

-   **Prop** is a special keyword in React, which stands for properties and is being used for passing data from one component to another.
-   Data with props are being passed in a uni-directional flow. (one way from parent to child)
-   Props data is read-only, which means that data coming from the parent should not be changed by child components.

### Using Props in React

1.  Firstly, define an attribute and its value(data).
2.  Then pass it to child component(s) by using Props.
3.  Finally, render the Props Data.

### Greet

```js
...
const Greet = (props) => {
  return(
  <h1> Greetings! {props.name} a.k.a {props.heroName}</h1>
  )
}
...
```

### App.js

```js
...
<Greet name = "Bruce" heroName = "Batman"/>
<Greet name = "Clark" heroName = "Superman"/>
<Greet name = "Diana" heroName = "Wonder Woman"/>
...
```