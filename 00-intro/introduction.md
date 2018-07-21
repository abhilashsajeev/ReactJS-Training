# Introduction to ReactJS ![React][logo]

React JS is a JavaScript library for building user interfaces. It only comprises of the view layer of any application.

Unlike Frameworks like Angular JS which contains all the parts of MVC ie, *Model, View, Controller* React contains only the **View** part.

React is useful areas where the data is changing continiously.

#### Problems with MVC
![SimpleMVC][mvcsimple]

**But this get complex**
![Complex MVC][mvccomplex]

React supports only one way data flow. When ever data changes we render the applications. But it will not be an expensive process like you think. It is because of React uses a algorithm called VIrtual DOM
**Virtual DOM:**
It is esssentially a light weight representaion of BrowserDOM. When ever data changes Reacts algorithm will compute the minimal components need to be altered and it will update only those components. No _Dirty checking_.
![Virtual DOM][vdom]

Current version of React contains two libraries one is **React** core library and the other is **ReactDOM** library.

They are available as CDN, npm , yarn packages.

The core library contains all the core functionlaities like virutalDOM implementation, component lifecycle methods and all.



ReactDOM contains two methods

```javascript
ReactDOM.render(<DomElement>, ElementTarget)
```

and

```javascript
ReactDOM.renderToString() // Used for server rendering
```
In React Everything is component. We visualise each component in a similar heirarchy to that of a DOM Tree. 

In a Single page application we will render all the application to a single DOM
You see this line at the root of react application

```javascript
var element = document.getElementById("root");
ReactDOM.render(<DomElement>/, element)

```
It is a convention to name React Components to name with Captialised format


### Let us see how a react component looks like

```javascript
class ShoppingList extends React.Component {
  render() {
    return (
      <div className="shopping-list">
        <h1>Shopping List for {this.props.name}</h1>
        <ul>
          <li>Instagram</li>
          <li>WhatsApp</li>
          <li>Oculus</li>
        </ul>
      </div>
    );
  }
}
```

This is a standard example taken from the react website itself. The **render** method consists of UI we want to show in the browser screen.

What is inside the return statement is not actually HTML it a syntax sugar developed by the react team to make our life easier its called **JSX**. It is very similar to our normal HTML DOM but will small differences one you can see is ` className` insted of standard `class`. 

There is alternate way rather than using the JSX. Using pure JavaScript functions. But we wont use it in actual coding. Why? You will see why in the below code.

It is similar to document.createElement but it is called `React.createElement`. this takes three arguments.

```javascript
React.createElement('<ElementType>', <ElementProperties>, <Children1>,<Children1>....)
```

Let us see the same code written using JSX and the hard way

**JSX**
```javascript
render(){
  return (
    <div className="shopping-list">
      <h1>Hello World </h1>
      <ul>
        <li>one</li>
        <li>two</li>
      </ul>
    </div>
  )
}
```

```javascript
return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', null, "Hello World"),
  React.createElement('ul', null,
   React.createElement('li', null, "one"),
   React.createElement('li', null, "two"))
);
```


Now you know why we will use JSX

We will use ECMAScript6 Standard to write ReactJS files


[vdom]: https://cdn-images-1.medium.com/max/1173/1*jb7rWNWkjLcGri_GZhxBGA.png "Virtual DOM example"
[logo]: https://cdn-images-1.medium.com/max/675/1*oi8WLwC2u0EEI1j9uKmwWg.png

[mvcsimple]:https://koenig-media.raywenderlich.com/uploads/2016/06/MVC-feature-250x250.png

[mvccomplex]:https://image.slidesharecdn.com/mvc2-161003142915/95/mvc-20-a-breakthrough-16-638.jpg?cb=1475505171