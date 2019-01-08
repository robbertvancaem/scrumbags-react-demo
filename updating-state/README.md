# Updating state

We're going to introduce a counter that indicates how many times a user has clicked a button.

## Result

You can see the HTML [here](index.html)

#### Introduce counter in state

We're going to add a variable called `counter` with a default value of 0 to the state in the constructor.

```javascript
this.state = {
  text: "Hello world",
  counter: 0
};
```

#### Define onClick handler

Next we're going to define an onClick function that gets called every time the user clicks the button. It has no arguments but increments the current value of `counter` by 1. To update the state, we're using React's `setState` function.

```javascript
onClick() {
  const counter = this.state.counter +1;
  this.setState({
    counter: counter
  })
}
```

#### Use the value for counter in the 'render' function

```javascript
render() {
  return (
    <div>
      <h1>{this.state.text}: #{this.state.counter}</h1>
      <button onClick={this.onClick}>Click to increment</button>
    </div>
  )
}
```

Notice how the render function returns a wrapping div that contains the title and button. This wrapping can be any element; a div, a span, or a [React Fragment](https://reactjs.org/docs/fragments.html) (an empty element that is not actually rendered into the DOM). React will throw an error when your render function returns multiple elements and is not contained by one wrapping tag.

#### Bind the onClick function in the constructor

If you click the button at this point, the console will show an error that property 'state' of undefined cannot be read. We need to give the `onClick` handler access to the 'this' scope by adding a line in our constructor.

```javascript
constructor(props) {
  super(props);
  this.state = {
    text: 'Hello world',
    counter: 0
  };
  this.onClick = this.onClick.bind(this);
}
```

Now if you open up the example in your browser, it will increment the number after 'Hello world'. Cool.
