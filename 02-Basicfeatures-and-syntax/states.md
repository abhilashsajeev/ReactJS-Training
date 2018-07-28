# States in ReactJS

State is a special property available in components that extends `Component`. ie state works only in components that looks like `class App extends Component`. This will not work with functional components. Still we should use function components more because we should use state with much more care. Having state in all your components and manipulating it from anywhere makes your app unpredictable.

We create a state with keyword state inside the class and assign an object.

```javascript
class App extends Component {
  state = {
    persons [
      {name: "Max", age: 21}
      {name: "Manu", age: 24}
      {name: "Amit", age: 28}
    ]
  }
  render(){
    // truncated content
  }
}
```

we can access state by `this.state` inside your jsx. Remember state is available inside the component. you can pass it to children.

```javascript
// Person.js
class App extends Component {
  state = {
    persons [
      {name: "Max", age: 21}
      {name: "Manu", age: 24}
      {name: "Amit", age: 28}
    ]
  }

  switchNameHandler  = ()=> {
    console.log("This was clicked")
  }
  render(){
    <div>
      <h1> Hellow world </h1>
      <button onClick={this.switchNameHandler}> Switch name </button>
      <Person name={this.state.persons[0].name} age={this.state.persons[1].age}/>
    </div>
  }
}
```


Whenever the value of state changes React **Re renders** the corresponding component. 

##### Note : Do not mutate state directly

We use a method called `setState` to change state. This will re render the component.

Concept of **container components**
Let us see this in [practice](https://codesandbox.io/s/5zzy5n761n)

Refs