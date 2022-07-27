# React.js
*For official docs on react.js visit https://reactjs.org/*

> This repo contains some important concepts and notes to understand and learn react.js

## What is React
It is a javascript library for building user interfaces created by facebook. It is only concerned with state management and rendering that state to the DOM.

### Reactive Confusion
By the word React it easily confuse itself with reactive programming. Lets simplify it.

A [programming paradigm](https://en.wikipedia.org/wiki/Programming_paradigm) is a fundamental style of computer programming. There are four main paradigms: 
1. [**Imperative**](https://en.wikipedia.org/wiki/Imperative_programming) - instructs the machine how to change its state, 
2. [**Declarative**](https://en.wikipedia.org/wiki/Declarative_programming) - instructs the machine what is to be done, but not how to compute it (which is done by underlying imperative logic)
3. Functional (subset of the declarative paradigm)
4. Object-oriented.

Example: To get array of doubled values of an array
```javascript
let value = [1,2,3,4];

// imperative approach
for (let i = 0; i < 4; i++) {
  value[i] = value[i] * 2;
}

// declarative approach
value = value.map(v => v * 2);
```
Here the map function define what is to be done by the having the imperative logic hidden inside the function. [`youtube`](https://youtu.be/E7Fbf7R3x6I)

[Reactive programming](https://en.wikipedia.org/wiki/Reactive_programming) is also a subset of declarative programming paradigm that relies on asynchronous programming logic to handle real-time updates to otherwise static content. 

For example, In imperative programming `a = b + c` would mean that the values of `b` and `c` can be changed with no effect on the value of `a`. In reactive programming, the value of `a` is automatically updated whenever the values of `b` or `c` change, without re-execution.

Example of reactive programing is [ReactiveX](https://rxjs.dev/) or to create one from scratch watch [`youtube`](https://youtu.be/zAPTohhQpg0)
