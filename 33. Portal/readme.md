#   Portals

Portals provide a first-class way to render children into a DOM node that exists outside the DOM hierarchy of the parent component.

### Syntax

```js
ReactDOM.createPortal(child, container)
```
>   The first argument (child) is any renderable React child, such as an element, string, or fragment. The second argument (container) is a DOM element.

### Usage

Normally, when you return an element from a component’s render method, it’s mounted into the DOM as a child of the nearest parent node:

However, sometimes it’s useful to insert a child into a different location in the DOM:

A typical use case for portals is when a parent component has an `overflow: hidden` or `z-index style`, but you need the child to visually **break out** of its container. For example, dialogs, hovercards, and tooltips.

### Things to consider when using Portals

-   **Event Bubbling will work as usual** — Event bubbling will work as expected by propagating events to the React tree ancestors, regardless of the Portal node location in the DOM.

-   **React has control over Portal nodes and its lifecycle** — When rendering child elements through Portals, React still has control over their lifecycle.

-   **Portals only affect the DOM structure** — Portals only affect the HTML DOM structure and not impact the React components tree.

-   **Predefine HTML mount point** — When using Portals, you need to define an HTML DOM element as the Portal component’s mount point.

### Folder-Structure
```
components
    +|__Portal.js
```

### index.html

```html
...
<html>
    ...
    <body>
        ...
        <div id="portal-root"></div>
    </body>
</html>
```

### Portal
```js

import React from 'react'
import ReactDOM from 'react-dom'

function Portal(){
  return ReactDOM.createPortal(
    <h1>
      Portal
    </h1>,
    document.getElementById('portal-root')
  )
}

export default Portal
```