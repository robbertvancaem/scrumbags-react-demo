# Basic

## Result

You can see the HTML [here](index.html)

## Scripts

This basic example shows how to render a React component in an HTML page. It is a simple HTML page with a few script tags:

`<script src="https://unpkg.com/react@16/umd/react.development.js"></script>` Developtment build of React  
`<script src="https://unpkg.com/react@16/umd/react.development.js"></script>` Development build of React-DOM

The difference between React and React-DOM is that the React package contains solely functionality for components, state, props etc, while the React-DOM package is the 'glue' between React and the DOM. The reason it is split is because of React Native. The React-DOM package is only used in web apps, while the React package is used in web apps ánd mobile apps.

`<script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>` Babel to transpile JSX. JSX is syntactical sugar to not have to write:

```javascript
return React.createElement("h1", attributes, "Hello world");
```

But instead write 'HTML' in your javascript:

```javascript
return <h1>Hello world</h1>;
```

## My first React component

To create our very first React component, we create a Javascript class called BasicComponent which extends React's Component class. This class will contain our logic for the BasicComponent.

```javascript
class BasicComponent extends React.Component {}
```

Next we're going to add a constructor to it

```javascript
class BasicComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { text: "Hello world" };
  }
}
```

The constructor accepts a parameter called 'props'. This constructor will be called before the component is mounted/rendered. Later we will see how we can make use of this.

A React component can also have a 'state'. In our case we define our state as an object with a key of 'text' and a value of 'Hello world'.

Next, we're going to actually render this text in a H1-tag. The 'render' method is the only method that _must_ be defined in a React component. It is a simple function that returns a H1 tag containing the text that comes from our state. Note the brackets around `{this.state.text}`.

```javascript
class BasicComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { text: "Hello world" };
  }

  render() {
    return <h1>{this.state.text}</h1>;
  }
}
```
