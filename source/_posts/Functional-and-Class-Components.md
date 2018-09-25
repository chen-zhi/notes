---
title: Functional and Class Components
date: 2018-09-25 12:34:05
tags: react
---

## Functional(Stateless) Component

A functional(a.k.a. stateless) component is just a plain javascript function which takes props as an argument and returns a react element.

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

## Class(Stateful) Component
Use an ES6 class to define a class component:

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
Class components offer more features, and with more features comes more baggage. The primary reason to choose class components over functional components is that they can have state.