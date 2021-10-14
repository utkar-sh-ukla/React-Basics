# List & Keys

- Keys are used to uniquely identify elements in a list and it helps react to identify what is added, updated and changed. Apart from that it helps react to efficiently update the DOM.

### NameList

```js
...
const personsList = persons.map(person => (<Person key = {person.id} person = {person} />))
...
```
