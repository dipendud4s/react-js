# Components

Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML. Components come in two types, 

## 1. Class components
```javascript
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}
```
Class components are made of
- Props as input
- JSX as output
- [State](State.md) for internal data
- setState calls
- [Lifecycle of Components](https://www.geeksforgeeks.org/reactjs-lifecycle-components/)  - initialization, mounting, updating and unmounting
  1. Initialization 
    - constructor()
    - getDefaultProps()
    - getInitialState()
  2. Mounting
    - componentWillMount()
    - render()
    - componentDidMount()
  3. Updating
    - When receiving new props from the parent
    
      ![alt text](https://miro.medium.com/max/1010/1*5fwo0VC1KtiWH64CENQ8dQ.png "Logo Title Text 1")
    
    - When the state changes via this.setState()
      
      ![alt text](https://miro.medium.com/max/1030/1*u0CoE_GHlUB4Ce-yZtgv0Q.png "Logo Title Text 1")
    
  4. Unmounting
    - componentWillUnmount()

  To get the order of execution [click here](https://medium.com/react-ecosystem/react-components-lifecycle-ce09239010df)

## 2. Function components
```javascript
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```
Functional components are made of
- Props
- JSX
- Hooks 
  - useState
  - useEffects
  - lot more

## Atomic structure

![Atomic](https://miro.medium.com/max/1400/1*PcQ-m317YX6ct9ccBi6H1Q.png "Atomic design pattern")



