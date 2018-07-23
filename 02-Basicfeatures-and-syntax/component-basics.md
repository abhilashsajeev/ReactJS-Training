# Components

Everything react is about are components. Components are awesome because we can focus our code in each file and hence make it more maintainable. They are also reuseable and configurable.

There are generally 2 types of React components.

```javascript
// App.js
import React, {Component} from "react"

class App extends Component {
  render(){
    return (
      <div className="heading">
        <h1> Hello world </h1>
      </div>
    )
  }
}

export default App;
```

- ### Functional components
```javascript
import React from "react"

const App = ()=> (
  <div className="heading">
    <h1> Hello world </h1>
  </div>
)


export default App
```

They are also called as **stateless components**. It is suggested that we should use it more.
Why? see below
1. More focused on presentation

React is forcing us to write components which are used only for presentational purpose, these components are useful for dumb presentational purpose only, that focus on UI rather than behaviour. Technically speaking its normal tendency to go for stateful components, doing that way we are making our code easily hackable where every damn component keeps its own local state. Functional components allowing us to have pure components which just focus on presentation. where as the state is maintained by few higher level components.

2. Gain in Performance

Stateless components will bring performance gain since there is no state and lifecycle of a component. React doesn’t need to have unnecessary check and memory allocations which eventually brings performance boost.

3. Clean and Optimised Code

Stateless components reduce lot of code, almost 20% – 30% reduction in code and hence the code will become clean and optimised.

4. Easy to debug

Functional components are pure components and helps your to analyse your code quickly and you no need to put log if assert calls everywhere to debug. 
Here in such components `render` method is necessary. Beacuse react will call this render method to render something to screen. It should return an HTML/JSX code **always**. The file extension can be .jsx or .js (Most confusing part !!)

----

## JSX Restrictions
Eventhough it is HTMLish we cannot use certain words that is reserved by JavaScript. One important example is `class` we use `className` when we write JSX. 
- JSX element should have one root element. See the wraping
- But this restriction has been lowered from React 16 onwards

#### Outputting a dynamic content [click here](dynamic-content.md)