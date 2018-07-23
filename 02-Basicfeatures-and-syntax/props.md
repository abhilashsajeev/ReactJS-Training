# Props in Reactjs

It would be great if we could pass some data to the Person component we have created earlier. or have a opening and closing tags and fill some data there too. Like a HTML tag.

```
// App.js

class App extends Component {
  render () {
    return (
      <div>
        <h1> Hello world </h1>
        <Person name="Manu" age="20"/>
        <Person name="Dhruv" age="21"> Some Other value to display </Person>
        <Person name="Amit" age="25"/>
      </div>
    )
  }
}
```

React takes such values and gives us access to receiving components in the name of **props**. We can access them by props.name and props.age

```javascript
// Person.js
const Person = (props)=> (
  <p> Hi {props.name} and his age is {props.age} </p>
)
```

We can access the contents passed between opening and closing tags in a slightly different way. This is actually super simple too. 

We can access a special props react gives us. This is called `children` property. This is a reserved word. React automatically passes the content of opening and closing tags to props.children automatically. 

```javascript
const Person = (props) => (
  <div>
    <p> Hi {props.name} and his age is {props.age} </p>
    {props.children}
  </div>
)
```

Let us code this ourself in practice [here](https://codesandbox.io/s/9jy8jjkzqo)

### [State](states.md)