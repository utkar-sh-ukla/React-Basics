#   JSX

-   JavaScript XML(JSX) - Extension to JavaScript Language Syntax.
-   Write XML like code for element & components.
-   JSX tags have a tag name, attribute & children.
-   JSX is not neccessity to write react Applications.
-   JSX makes your react code simple & elegant.
-   JSX ultimately transpiles to pure JavaScript which is understood by browser.

### Folder Structure

```
components
    +|__Hello.js
```

### Hello 

```js
import React from 'react'

const Hello = () => {
  return React.createElement('div', null, React.createElement('h1', null, 'Hello React'));
}

export default Hello
```

### JSX differences

-   class -> className
-   for -> htmlFor
-   camelCase for naming convention 
    -   onclick -> onClick
    -   tabindex -> tabIndex 

