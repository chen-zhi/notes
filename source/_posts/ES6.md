---
title: ES6
date: 2018-09-26 14:27:39
tags: JavaScript
---

## var. let and const

### var
Declares a variable, optionally initializing it to a value.
### let
Declares a block-scoped, local variable, optionally initializing it to a value.
### const
Declares a block-scoped, read-only named constant.
### Hoisting
In ECMAScript 2015, let (const) does not hoist the variable to the top of the block. Referencing the variable in the block before the variable declaration results in a ReferenceError. The variable is in a "temporal dead zone" from the start of the block until the declaration is processed.

## Arrow Function
`() => { statements }`
### Lexical this
Unlike functions, arrows share the same lexical this as their surrounding code.

## Spread and Rest
`...`

## Destructuring
The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
### Array destruring
```
var foo = ['one', 'two', 'three'];

var [one, two, three] = foo;
console.log(one); // "one"
console.log(two); // "two"
console.log(three); // "three"
```
### Object destructuring
```
var o = {p: 42, q: true};
var {p, q} = o;

console.log(p); // 42
console.log(q); // true
```

## Template String
```
let firstName = 'John',
    lastName = 'Doe';
 
let greeting = `Hi ${firstName}, ${lastName}`;
console.log(greeting); // Hi John, Doe
```
## Module
* import
* export

## Class

### Class declaration
```
class Animal {
    constructor(type) {
        this.type = type;
    }
    identify() {
        console.log(type);
    }
}
 
let cat = new Animal('Cat');
cat.identify();
```
1. Not hoisted: class declarations are not hoisted like function declarations
2. Strict mode: all the code inside a class executes in strict mode automatically, and you cannot change this behavior.

### Getter and setter

### Inheritance Using extends & super

## Promise
The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value.
### State
A Promise is in one of these states:
* pending: initial state, neither fulfilled nor rejected.
* fulfilled: meaning that the operation completed successfully.
* rejected: meaning that the operation failed.

### Chaining

## Generator
Generators simplify iterator-authoring using `function*` and `yield`. A function declared as function* returns a Generator instance. Generators are subtypes of iterators which include additional `next` and `throw`. 

## Map and Set
### Map
The Map object holds key-value pairs. Any value (both objects and primitive values) may be used as either a key or a value.