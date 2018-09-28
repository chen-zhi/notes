---
title: Handling Events in React
date: 2018-09-25 16:13:44
tags: React
---
## Difference between DOM Events and React SyntheticEvents
* HTML: onclick  React: onClick
* Cannot return false to prevent default behavior in React. Use preventDefault instead.

## React Event Handler

### Recommended: Binding this in the constructor
```
class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = {isToggleOn: true};

    // This binding is necessary to make `this` work in the callback
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(state => ({
      isToggleOn: !state.isToggleOn
    }));
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        
{this.state.isToggleOn ? 'ON' : 'OFF'}
      </button>
    );
  }
}

ReactDOM.render(
  <Toggle />,
  document.getElementById('root')
);
```

### Using public class fields syntax (experimental)
Click [here](http://2ality.com/2017/07/class-fields.html) to read more.
```
class LoggingButton extends React.Component {
  // This syntax ensures `this` is bound within handleClick.
  // Warning: this is *experimental* syntax.
  handleClick = () => {
    console.log('this is:', this);
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        Click me
      </button>
    );
  }
}
```

### Using arrow function
If this callback is passed as a prop to lower components, those components might do an extra re-rendering.

```
class LoggingButton extends React.Component {
  handleClick() {
    console.log('this is:', this);
  }

  render() {
    // This syntax ensures `this` is bound within handleClick
    return (
      <button onClick={(e) => this.handleClick(e)}>
        Click me
      
</button>
    );
  }
}
```

### With createReactClass()
The React team has explained this in their docs [here](https://reactjs.org/docs/react-without-es6.html#autobinding).
With `createReactClass()`, this is not necessary because it binds all methods. 
```
class SayHello extends React.Component {
  constructor(props) {
    super(props);
    this.state = {message: 'Hello!'};
    // This line is important!
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    alert(this.state.message);
  }

  render() {
    // Because `this.handleClick` is bound, we can use it as an event handler.
    return (
      <button onClick={this.handleClick}>
        Say hello
      </button>
    );
  }
}
```
The above code works the same as the following.
```
var SayHello = createReactClass({
  getInitialState: function() {
    return {message: 'Hello!'};
  },

  handleClick: function() {
    alert(this.state.message);
  },

  render: function() {
    return (
      <button onClick={this.handleClick}>
        Say hello
      </button>
    );
  }
});
```

## Understand this
In JavaScript, class methods are not bound by default.

### This as a DOM event handler

When a function is used as an event handler, its this is set to the element the event fired from (some browsers do not follow this convention for listeners added dynamically with methods other than addEventListener).

```
<!DOCTYPE html>
<html>
<body onclick="myFunction(event)">

<p>Click on a paragraph. An alert box will alert the element that triggered the event.</p>

<p><strong>Note:</strong> The target property returns the element that triggered the event, and not necessarily the eventlistener's element.</p>

<script>
function myFunction(event) { 
    alert(event.target.nodeName);
}
</script>

</body>
</html>
```

### This as a constructor
When a function is used as a constructor (with the new keyword), its this is bound to the new object being constructed.