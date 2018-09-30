---
title: Redux 101
date: 2018-09-29 00:53:43
tags: 
- React
- Others
---

Redux is a predictable **state container** for JavaScript apps.

## Installing 
### Redux
```
npm install --save redux
```
### React Redux
```
npm install --save react-redux
```

## Connect the Store
First, we will use Redux’s `createStore()` method to create a store from our reducer. Because we want to be able to dispatch asynchronous actions, we will also use `thunkMiddleware` from the `redux-thunk` module. To use middleware in our store, we’ll use Redux’s `applyMiddleware()` method.
```
const store = createStore(reducer, applyMiddleware(thunkMiddleware));
```

## Reducers
Reducers specify how the application's state changes in response to actions sent to the store. Remember that actions only describe what happened, but don't describe how the application's state changes.

## Actions
Actions are **payloads** of information that send data from your application to your store. They are the only source of information for the store. You send them to the store using `store.dispatch()`.

