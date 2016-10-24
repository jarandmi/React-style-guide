# React-style-guide

Naming

Use PascalCase for alle React component. Both filenames and component names.
```javascript
//Example
import List from "./list.js"
```

If you have interal state or use refs, use class

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
```javascript
<List />
```

If more than one attribute format over multiple lines
```javascript
//Example with one attribute
<List name="Item list" />

//Example with multiple attributes
<List 
  name="Item liste"
  label="List of items"
/>
```

Use spacing inside curly braces
```javascript
//Example
<List content={` `this.props.items` `} />
```

- Use camelCase for prop names.
- Wrap return inside parentheses when more than one line
```javascript
render() {
  return <div>List</div>
}

render (){
  return(
    <ul>
      <li>List item</li>
      <li>List item</li>
    </ul>
  )
}
```

- Always self-close tags that have no children
- Inline interation with arrow function
```javascript
//Example with single parameter (don't use parentheses)
return(
  <div>{ 
    this.props.list.map(item => (
      <ListItem key={ item.key } />
    ))
  }</div>
)

//Example with multiple parameters
return(
  <div>{ 
    this.props.list.map((item, index) => (
      <ListItem 
        key={ items.index }
        name={ item.name }
      />
        
    ))
  }</div>
)
```

Binding
```javascript
//Example of autobinding `this` in ES6
class List extends React.Component {
  checkItem = () => {
    ...
  }
  
  render(){
    return(){
      <div onClick={ this.checkItem }>Check</div>
    }
  }
}
````

Ordering inside a Component
1. `constructor`
2. Lifecycle functions in the order they execute
3. clickHandlers
4. Other functions
5. `render()`
