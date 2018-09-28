---
title: TypeScript
date: 2018-09-28 12:23:57
tags: JavaScript
---

## What's TypeScript
TypeScript is a superset of JavaScript. By convention, TypeScript files are named with a .ts extension, and they
will need to be compiled to standard JavaScript, usually at build time, using the TypeScript
compiler. The generated code is very readable.
### Installing via npm
```
npm install -g typescript
```
### Compiling
```
tsc test.ts
```
## Types
Syntax:
```
let variable: type;
```
## Return Types
You can also set the return type of a function:
```
function startRace(race: Race): Race {
race.status = RaceStatus.Started;
return race;
}
```
If the function returns nothing, you can show it using void:
```
function startRace(race: Race): void {
race.status = RaceStatus.Started;
}
```
## Enums
TypeScript offers enum.

## Interfaces
duck typing