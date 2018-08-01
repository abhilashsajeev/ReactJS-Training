### Adding dynamic contents

We can take the person functional component, from the earlier example.
In order to add some dynamic content we can wrap it in `{}`. See the example

```javascript
// Person.js

import React form "react"

const Person = ()=> (
  <p> I am a person and I am {Math.floor(Math.random()* 30)} years old </p>
)

```

We can write only one line expressions / function returns here. Not a JavaScript classes or such big tasks.
We will use this type of modifications and dynamism throughout the use of Reactjs

Let us see it in [Practical](https://codesandbox.io/s/9jy8jjkzqo)

Rather than using some generic content how about making our component more dynamic? We will see it [here](props.md)

