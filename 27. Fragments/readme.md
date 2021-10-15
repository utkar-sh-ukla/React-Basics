# Fragments

- A common pattern in React is for a component to return multiple elements. 
- Fragments let you group a list of children without adding extra nodes to the DOM.

### syntax

```js
...
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
...
```

> Fragments declared with the explicit `<React.Fragment>` syntax may have `keys`. `key` is the only attribute that can be passed to Fragment.

### short syntax

```js
...
render() {
  return (
    <>
      <ChildA />
      <ChildB />
      <ChildC />
    </>
  );
}
...
```

> You can use `<> </>` the same way you’d use any other element except that it doesn’t support `keys` or attributes.

