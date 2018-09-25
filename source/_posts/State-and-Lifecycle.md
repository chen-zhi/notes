---
title: State and Lifecycle
date: 2018-09-25 19:06:27
tags: react
---
## State
A component needs state when some data associated with it changes over time.
In React components, state is an object. 

### Do Not Modify State Directly
Never modify state outside of this.setState().

#### Do not use array mutating methods
* push(), pop()
* shift(), unshift()
* splice()

#### Use nonmutating methods
* add: concat(), spread operator
* delete: filter(), slice()
* replace: map()
* Object.assign()

### setState() is Asynchronous

## Lifecycle Methods
We can declare special methods on the component class to run some code when a component mounts and unmounts
### componentDidMount()

### componentWillUnmount()