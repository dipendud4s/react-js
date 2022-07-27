# State Pattern

The state pattern is a [behavioral software design pattern](https://en.wikipedia.org/wiki/Software_design_pattern) that allows an object to alter its behavior when its internal state changes. In simple words it the variable by changing which effects the result or behavior of the object (components in react).

This pattern is close to the concept of [finite-state machines](https://en.wikipedia.org/wiki/Finite-state_machine).

Example of a **finite state machine**
```javascript
const machine = {
    state: 'OFF', // initial state
    // this are possible transitions for different states
    transitions: {
        OFF: {
            press() {
                this.state = 'ON';
            }
        },
        ON: {
            press() {
                this.state = 'OFF';
            },
        },
    },
    // method to trigger a transition
    dispatch(actionName) {
        const action = this.transitions[this.state][actionName];
        if (action) {
            action.call(this);
        } else {
            console.log('invalid action');
        }
    },
};
const flashlight = Object.create(machine);

console.log(flashlight.state); // OFF
flashlight.dispatch('press'); 
console.log(flashlight.state); // ON
```

One important thing that differentiate state machine to React State is the fact that this changes of state doesn't have an **effect** or a **side effect** In order to do that Lets introduce a function `setState` instead of `dispatch` and remove `transitions`

Example of a **state like in react**
```javascript
const machine = {
    state: 'OFF', // initial state
    // method to trigger a transition
    setState(newState) {
        this.state = newState;
        this.effect();
    },
    // side effect from any transition
    effect() {
      if(this.state === 'ON') {
        console.log('Its is bright');
      } else if(this.state === 'OFF') {
        console.log('Its is dark');
      } else {
        console.log('Something went wrong');
      }
    }
};
const flashlight = Object.create(machine); 

flashlight.setState('ON'); // Its is bright
flashlight.setState('OFF'); // Its is dark
```
Here the `setState` method is need in order to change the behaviour of the flashlight component. and also there are no pre defined transitions of the state.

To learn about different design patters [`youtube`](https://youtu.be/tv-_1er1mWI)