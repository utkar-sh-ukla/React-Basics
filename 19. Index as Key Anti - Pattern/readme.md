# Index as a key

When to use index as a key?

- Items in your list do `not` have a `unique id`.
- The list is a static list & will not change.
- The list will never be reordered or filtered.

### NameList
```js
...
const names = ["Bruce", "Diana", "Clark"]

const nameList = names.map((name, index) => (<h2 key = {index} > {index} {name}</h2>))

return <div>{nameList}</div>
...
```