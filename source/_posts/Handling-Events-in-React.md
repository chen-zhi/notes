---
title: Handling Events in React
date: 2018-09-25 16:13:44
tags: react
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