---
title: React 101
date: 2018-09-28 20:14:39
tags: React
---

# Zero-Configuration Setup
Use **create-react-app** to bootstrap the application.

To install:
```
npm install -g create-react-app
```

# JSX
JSX is a **XML-like syntax extension** to JavaScript. 
React builds our apps with a fake representation of the Document Object Model (DOM). React calls this the **virtual DOM**.
## CamelCase property
Since JSX is closer to JavaScript than to HTML, React DOM uses camelCase property naming convention instead of HTML attribute names.
For example, class becomes className in JSX, and tabindex becomes tabIndex.
## Expressions in JSX
```
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```
## Compiling
**Babel** compiles JSX down to React.createElement() calls.
`React.createElement(component, props, ...children)`
These two examples are identical:
```
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```
```
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```
# Rendering Elements
To render a React element into a root DOM node, pass both to ReactDOM.render():
```
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
```
# Components
React lets you define components as classes or functions.
**The only** method you must define in a React.Component subclass is called **render()**. All the other methods described on this page are optional.
## Functional and Class Components
Read more in [Functional and Class Components](/2018/09/25/Functional-and-Class-Components/) blog.
## Props
Probs are read-only.
### PropTypes
```
import PropTypes from 'prop-types';

class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};
```
### children
You can put a string between the opening and closing tags and `props.children` will just be that string. This is useful for many of the built-in HTML elements. For example:
```
<MyComponent>Hello world!</MyComponent>
```
This is valid JSX, and `props.children` in `MyComponent will` simply be the string `"Hello world!"`. 
## State and Lifecycle
Read more in [State and Lifecycle](/2018/09/25/State-and-Lifecycle/) blog.

# Handling Events
Read more in [Handling Events in React](/2018/09/25/Handling-Events-in-React/) blog.

# Conditional Rendering
## if-else

## ternary operator
`condition ? true : false`

## logical && operator
It works because in JavaScript, true && expression always evaluates to expression, and false && expression always evaluates to false.

Therefore, if the condition is true, the element right after && will appear in the output. If it is false, React will ignore and skip it.

# Lists and Keys
## Lists
Use Array map mathod to transform arrays into lists of elements.
## Keys
Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.

# Forms
In HTML, form elements such as `input`,` textarea`, and `select` typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().

```
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

Read more in [Forms in React](/2018/09/27/Forms-in-React/) blog.

# Routing
Visit website of [React Router](https://reacttraining.com/react-router/)
