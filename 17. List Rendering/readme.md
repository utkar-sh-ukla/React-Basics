# List Rendering

### Folder Structure

```
components
    +|__NameList.js
    +|__Person.js
```

### NameList

```js
import React from 'react'
import Person from './Person'

function NameList() {
  const persons = [
    {
      id: 1,
      name: "Bruce",
      age: 30,
      skill: "React"
    },
    {
      id: 2,
      name: "Clark",
      age: 25,
      skill: "Angular"
    },
    {
      id: 3,
      name: "Diana",
      age: 28,
      skill: "Vue"
    }
  ]
  
  const personsList = persons.map(person => (<Person person = {person} />))

  return <div>{personsList}</div>
}

export default NameList
```

### Person

```js
import React from 'react'

function Person({person}){
  return(
    <div>
      <h2>I am a {person.name}. I am {person.age} years old. I know {person.skill}</h2>
    </div>
  )
}

export default Person
```
