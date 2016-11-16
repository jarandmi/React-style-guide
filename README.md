# React-style-guide

##Naming

Use PascalCase for all React components. Both file and component names.
```javascript
import List from './List.js'
```

##Class and stateless function

If you have interal state or use refs, use class

```javascript
class Item extends from React.component {
  ...
  render() {
    return (<div>{ this.state.items }</div>)
  }
}
```

If you don’t need state or to use refs, use a stateless component.

```javascript
// With block statement
const Item = ({ items } = props ) => {
  return (
    <div>{ items }</div>
  )
}

// With implicit return
const Item = ({ items } = props ) => (
  <div>{ items }</div>
)
```

##Formatting

- Always use single space before closing tag
```javascript
<List />
```

- If more than one attribute format over multiple lines
```javascript
// With one attribute
<List name="Item list" />

// With multiple attributes
<List 
  name="Item liste"
  label="List of items"
/>
```

- Use spacing inside curly braces
```javascript
<List content={ this.props.items } />
```
- Use camelCase for prop names.
- Wrap return statements inside parenthesis when there are more than one line
```javascript
render() {
  return <div>List</div>
}

render() {
  return (
    <ul>
      <li>List item</li>
      <li>List item</li>
    </ul>
  )
}
```

Use double quotes on attributes, but single quots for all other.
```javascript
  <List 
    name="List name" 
    style={{ fontSize: '1rem' }} 
  />
```

- Always self-close tags that have no children

##Inline Functions
- Inline iteration with arrow function

```javascript
// With single parameter (don't use parenthesis)
return (
  <div>{ 
    this.props.list.map(item => (
      <ListItem key={ item.key } />
    ))
  }</div>
)

// With multiple parameters
return (
  <div>{ 
    this.props.list.map((item, index) => (
      <ListItem 
        key={ index }
        name={ item.name }
      />
        
    ))
  }</div>
)
```

##Binding

```javascript
// Autobinding `this` with arrow function in ES6
class List extends React.Component {
  checkItem = () => {
    this...
  }
  
  render() {
    return <div onClick={ this.checkItem }>Check</div>
  }
}
```

##Ordering

Ordering inside a Component
- 1. `constructor`
- 2. Lifecycle functions in the order they execute
- 3. clickHandlers
- 4. Other functions
- 5. `render()`
