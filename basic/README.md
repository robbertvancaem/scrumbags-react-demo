# Basic

## Demo

You can see the demo [here](index.html)

## Explanation

This basic example shows how to render a React component in an HTML page. It is a simple HTML page with a few script tags:

`<script src="https://unpkg.com/react@16/umd/react.development.js"></script>` Developtment build of React  
`<script src="https://unpkg.com/react@16/umd/react.development.js"></script>` Development build of React-DOM

The difference between React and React-DOM is that the React package contains solely functionality for components, state, props etc, while the React-DOM package is the 'glue' between React and the DOM. The reason it is split is because of React Native. The React-DOM package is only used in web apps, while the React package is used in web apps ánd mobile apps.

`<script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>` Babel to transpile JSX. JSX is syntactical sugar to not have to write:

```
return React.createElement('h1', attributes, 'Hello world');
```

But instead write 'HTML' in your javascript:

```
return (<h1>Hello world</h1>)
```
