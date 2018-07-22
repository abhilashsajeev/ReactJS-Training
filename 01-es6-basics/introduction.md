
# ES6 Basics
This is new upcoming standard for javascript. It may seem bit unfamiliar compared to the normal javascript we use. React apps are built with latest version of javascript. Using next gen features help us writing clean and robust code.

## `let` and `const`
 Both are different ways of creating variables. Older javascript uses a keyword `var` to create a variable. There is few key differences from var in let and const.

 `const` is used to declare varibles that does not change.

 `let` is a new way perhaps to create a variable. 

 A Major difference in this new keywords in relation with that of `var`is the scope of the variable. 

The `var` had a function level scope but the `let` have a block level that is between curly braces('{}').
 for Example
 ```javascript
function greet(name){
  var message = "Hello";
  if(name){
    var message = "Hello" + name
    return message
  } else {

  }

}
 ```

 ```javascript
 function greet(name){
   const message = "Hello";
   if(name){
     message = message + name // Triggers an error
   }
 }
 ```
 ---
## Arrow functions
A new syntax for creating new javascript function an example arrow function and normal function is shown below
```javascript
var myFunction = function () {
  console.log("Hello world")
}

var myArrowFunction = ()=> {
  console.log("Hellow world")
}
```

Arrow function also has added advantage of binding the context in which it runs to the function automaticaly. Avoiding using bind functions in may cases

```javascript
// just for demo purposes
var Person = function(name){
  this.name = name;
  this.greet = function(){
    console.log("Printing", this.name)
    var addHello  =  function(){
      console.log("Hello" + this.name) //  Throws an error since here this will be window
    }
    addHello();
  }
}

var manu = new Person("Manu")
manu.greet();
```

```javascript
var Person = (name)=>{
  this.name = name;
  this.greet = ()=>{
    console.log("Printing", this.name)
    var addHello  =  ()=>{
      console.log("Hello" + this.name) //  Runs without an error since this is already binded.
    }
    addHello();
  }
}

var manu = new Person("Manu")
```
---
## Exports and Imports
Sample is given along with different syntaxes for different imports and exports
```es6

// Person.js

let person = {
  name: "Ram"
}

export default person
```
the export default means if we require this file we get person object.

```javascript
// utils.js
export const clean  = ()=> return []
export const balance = 10
```

This can be imported in another file as
```javascript
// app.js
import person from './Person.js'

import {clean} from './utils'

import {balancedPayment as bsp} from './Person.js'
```

Ie the new technology says it an answer against some of the attrocities commited by the different people. 

---
## Understanding classes
ES6 class is a syntactic sugar for JavaScript function constructor. It is not similar to class in java. This also uses same prototypial inheritance of javascript, but in a new clean way.

classes are blue prints of objects. class can have both properties and methods.
```javascript
class Person {
  name = "John" // property
  callfn = ()=>{} // method in es7 way
}
```
class in instantiated with the `new` keyword similar to function consturctors.
```javascript
class Person {
  name = "John" 
  greet = ()=>{console.log("Hi " + this.name)} 
}

let john = new Person();
john.greet(); // outputs "Hi John"
```

Inheritance is also supported with `extends` keyword.

classes are used by react to create components.
**Now let us see an example for better understanding**
***

But we use a modern syntax of es7 in our projects.

```javascript

//es6 
class Person {
  constuctor(){
    this.name = "John"
  }
  greet(){
    console.log("Hello " + this.name)
  }
}

// es7
// No need to call in case of inheritance too !
class Person {
  name = "John"
  greet = ()=> {
    console.log("Hello", this.name)
  }
}

```
---


## Spread and Rest operator
Visually this is one operator `...` yes the three dots! We call it spread or rest depends on where we use it.

**Spread** operator is used to split up array elements or object properties.

```javascript
const oldArray = [1,2,3,4]
const newArray = [...oldArray, 5, 6]

const oldObject = {
  a: 1,
  b: 2
}

const newObject = {...oldObject, newProp: 5} // will overwrite
```

**Rest** operator is used to merge a list of function arguments into an array

```javascript
function sortArgs(...args){
  return args.sort()
}
```

#### Destructuring
Destructuring allows us to pull out elements or properties and store them in variables or arrays

```javascript
// Array destructuring
[a, b] = ["Hello", "Max"]
console.log(a)
console.log(b)


// Object destructuring
{name} = {name: "Max", age: 20}
console.log(name)
```

Note : strings, boolean, and numbers are primitive types and Objects and arrays are reference types

```javascript
const person = {
  name: "Manu",
  age: 24
}

let secondPerson = {...person} // copying

secondPerson.name = "Max"
console.log(secondPerson);

```

----
## Array functions

Just Refresh your ideas in javascript map function

```javascript

const singleArray = [1,2,3]

let doubleArray = singleArray.map((num)=> {
  return num * 2
}) // [2, 4, 6]
```