# React-style-guide

Naming

Use PascalCase for alle React component. Both filenames and component names.
```javascript
//Example
import List from "./list.js"
```

If you have interal state or use refs use class [classname] extends React.Component

```javascript
//example
class Item extends from React.component {
  ...
  render{
    return(<div>{ this.state.items}</div>)
  }
}
```

If you don't need state or use refs, use stateless arrow functions.

```javascript
//example with block statement
const Item = ({ items } = props ) => {
  return(
    <div>{ this.props.items</div>
  )
}

//Example with implicit return
const Item = ({ items } = props ) => (
  <div>{ items }</div>
)
```

- Always use single space before closing tag


