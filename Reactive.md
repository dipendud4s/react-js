# Reactive Confusion
By the word React it easily confuse itself with reactive programming. Lets simplify it.

## Programming paradigm
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

## Reactive programming

[Reactive programming](https://en.wikipedia.org/wiki/Reactive_programming) is also a subset of declarative programming paradigm that relies on asynchronous programming logic to handle real-time updates to otherwise static content. 

For example, 
```javascript
let a = b + c
// In imperative a will not change with b and c

// Now lets assume it is reactive 
let a = f(b, c)
// a is automatically updated whenever the values of b or c change, without re-execution. 
// This can be done if the following are true 

typeof a // observer
typeof b // observable
typeof f // subscription fuction
```
This pattern is called [reactive design pattern](https://reactivex.io/documentation/observable.html). Example of reactive programing is [RxJs](https://rxjs.dev/), [S.js](https://github.com/adamhaile/S) or to create one from scratch watch [`youtube`](https://youtu.be/zAPTohhQpg0)

## Is React not reactive?
React is made of
  - Components which are driven off 
    - State instead of observables
    - setState calls which are sort of like data change events. 
    - Hooks to add specific features
    - JSX are basically declarative. 
    - VDOM for better diffing

So what's the issue here? Here the expression is like 
```javascript
let Component = function() {
  [state, setState] = Hook();
  return JSX;
}
```
Here whenever `setState` is called the component re-executes itself to get the latest updates, although it has VDOM to only render the latest difference to the actual DOM.