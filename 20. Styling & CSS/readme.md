# Styling & Css 

There are 4 methods for Styling

- CSS StyleSheet
- Inline Styling
- CSS Modules
- CSS in JS Libraries (`Styled Components`)


## CSS StyleSheet

### Folder Structure
```
components
    +|__StyleSheet.js
    +|__myStyles.css
```

### StyleSheet

```js
import React from 'react'
import './myStyles.css'

function StyleSheet(props){
  let className = props.primary ? 'primary' : ''
  return(
    <div>
      <h1 className ={`${className} font-xl`}>StyleSheet</h1>
    </div>
  )
}

export default StyleSheet
```

### myStyles

```css
.primary{
  color: orange
}

.font-xl{
  font-size: 72px
}
```

### App
```js
<StyleSheet primary={true}/>
```

## Inline Styling

### Folder Structure
```
components
    +|__Inline.js

```
### Inline

```js
import React from 'react'

const heading = {
  fontSize: '72px',
  color: 'blue'
}

function Inline(){
  return(
    <div>
      <h2 style = {heading}> Inline </h2>
    </div>
  )
}

export default Inline
```

## CSS Modules

### Folder Structure

```
src
  +|__appStyles.css
  +|__appStyles.module.css

```

### App

```js
import './appStyles.css'
import styles from './appStyles.module.css'

...

<h1 className = 'error'>Error</h1>
<h1 className = {styles.success}>Success</h1>

...
```

### appStyles

```css
.error{
  color: red
}
```

### appStyles.module.css

```css
.success{
  color: green
}
```